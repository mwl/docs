---
description: Create alerts in ilert from CloudWatch alarms.
---

# Amazon CloudWatch Integration

Amazon CloudWatch is a monitoring service for AWS cloud resources and applications running in the AWS Cloud. Amazon CloudWatch can monitor AWS resources, such as EC2 instances, Amazon DynamoDB tables, and Amazon RDS DB instances, as well as application and service generated metrics and log files.

With ilert's CloudWatch integration, you can automatically create alerts in ilert from CloudWatch alarms. That way, you will never miss a critical alert and always alert the right person using ilert's on-call schedules, automatic escalation, and multiple alerting channels. When CloudWatch creates an alarm, ilert will alert the on-call person through their preferred channel, including SMS, phone calls, push notifications and Slack. ilert will automatically escalate to the next person, if the alert is not acknowledged. ilert also lets you define alerting rules based on support hours and delay alerts until your support hours start.

## In ilert: Create CloudWatch alert source <a href="#create-alert-source" id="create-alert-source"></a>

1. Switch to the tab "alert sources" and click on the button "Create new alert source"
2. Assign name and select escalation chain
3. Select and save "Amazon CloudWatch" in the Integration Type field.

![](<../.gitbook/assets/cw1 (1) (1) (1).png>)

1. The URL shown on the next page is the HTTP endpoint for the SNS topic in Amazon and will be needed in later steps.

![](../.gitbook/assets/cw2.png)

## In AWS SNS: create topic <a href="#create-topic" id="create-topic"></a>

> If you have already created an SNS topic for your CloudWatch alarms that you want to reuse, you can proceed to step 3.

1. In the SNS Dashboard click on "Create topic"

![](../.gitbook/assets/cw3.png)

1. Name the topic and click on "Create topic".

![](../.gitbook/assets/cw4.png)

1. Click on "Create subscription" on the Topic Detail page

![](../.gitbook/assets/cw5.png)

1. Select "HTTPS" as the protocol and transfer the URL from the above-created alert source to ilert at Endpoint and click on "Create subscription".

![](../.gitbook/assets/cw6.png)

1. The subscription is automatically confirmed by ilert when it is created. After updating the overview, the status "PendingConfirmation" should disappear and the ID should be displayed.

![](../.gitbook/assets/cw7.png)

## In AWS CloudWatch: Create alarm and link to topic <a href="#create-alarm" id="create-alarm"></a>

You can now link any CloudWatch alarm to the topic you have created. The following section describes how to create an alarm and make the link.

1. In CloudWatch, on the Alarms tab, click Create Alarm and select a metric

![](../.gitbook/assets/cw8.png)

1. Click on "+ Notification" to add two "Notification Actions": one for the states ALARM and OK. In the "Send notification to:" box, select the topic created above.

![](../.gitbook/assets/cw9.png)

![](../.gitbook/assets/cw10.png)

## FAQ <a href="#faq" id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes, as soon as the condition of an alarm is OK again in CloudWatch, the alert in ilert will be fixed.

**Can I link CloudWatch to multiple alert sources in ilert?**

Yes, create an SNS topic in CloudWatch for each alert source. You can then select for each alert in CloudWatch which topic you want to use for alerting.
