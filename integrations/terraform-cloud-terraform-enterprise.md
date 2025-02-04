---
description: >-
  With the ilert Terraform Cloud integration, you can create alerts in ilert
  based on Terraform Cloud runs.
---

# Terraform Cloud / Terraform Enterprise

## In ilert <a href="#in-ilert" id="in-ilert"></a>

### Create a Terraform Cloud alert source <a href="#create-alert-source" id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click **Create new alert source**
2. Enter a name and select your desired escalation policy. Select "Terraform Cloud" as the **Integration Type** and click on **Save**.

![](../.gitbook/assets/Screenshot\_25\_02\_21\_\_22\_56.png)

1. On the next page, a Webhook URL is generated. You will need this URL below when setting up the notification in Terraform Cloud.

![](../.gitbook/assets/Screenshot\_25\_02\_21\_\_22\_57.png)

## In Terraform Cloud / Terraform Enterprise <a href="#in-splunk" id="in-splunk"></a>

### Create a notification setting <a href="#create-action-sequences" id="create-action-sequences"></a>

1. Go to Terraform Cloud and then to **Your Workspace -> Settings -> Notifications**

![](../.gitbook/assets/Screenshot\_25\_02\_21\_\_22\_59.png)

1. On the next page,  click on the **Create a Notification** button

![](../.gitbook/assets/Screenshot\_25\_02\_21\_\_23\_03.png)

1. On the next page, name the  notification setting e.g. ilert, paste the **Webhook URL** that you generated in ilert, in the **Triggers** section choose **Only certain events** and select **Completed** and **Errored** options, then click on the **Create a Notification** button

![](../.gitbook/assets/Screenshot\_25\_02\_21\_\_23\_06.png)

Finished! Your Terraform Cloud run problems will now create alerts in ilert.

## FAQ <a href="#faq" id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes, as soon as an alert has been completed in Terraform Cloud, the associated alert in ilert will be resolved automatically.

**Can I connect Terraform Cloud with multiple alert sources from ilert?**

Yes, simply add more notification settings in Terraform Cloud.
