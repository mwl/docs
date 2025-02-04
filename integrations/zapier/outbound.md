---
description: >-
  User ilert as the trigger in Zapier and perform any action in Zapier for new
  or updated alerts in ilert.
---

# Zapier Outbound Integration

## In Zapier <a href="#in-ilert" id="in-ilert"></a>

### Create a Zap <a href="#create-action-sequences" id="create-action-sequences"></a>

1. Go to Zapier and click on **Make a Zap**

![](../../.gitbook/assets/Screenshot\_29\_10\_20\_\_16\_22.png)

1. On the next page, search for **iLert** trigger source and choose it:

![](../../.gitbook/assets/Edit\_a\_Step\_\_\_Zapier.png)

1. In the section **Trigger Event** choose **New or Updated Alert** and click on the **Continue** button

![](<../../.gitbook/assets/Edit\_a\_Step\_\_\_Zapier (1).png>)

1. On the next slide, choose your ilert account. Then click on the **Continue** button.

![](<../../.gitbook/assets/Edit\_a\_Step\_\_\_Zapier (2).png>)

1. On the next slide, choose **an alert source** and **trigger types** e.g. Alert Created. Then click on the **Continue** button.

{% hint style="warning" %}
NOTE: you can't use an Zapier alert source here, as it will lead to an infinite loop
{% endhint %}

![](<../../.gitbook/assets/Edit\_a\_Step\_\_\_Zapier (3).png>)

1. On the next slide, click on the **Test Trigger** button to see example data. Then click on the **Continue** button.

![](<../../.gitbook/assets/Edit\_a\_Step\_\_\_Zapier (4).png>)

1. Now you can **add any action** available in Zapier, e.g. Jira to create a ticket on your Jira board

![](../../.gitbook/assets/Edit\_Step\_\_\_Zapier.png)

## FAQ <a href="#faq" id="faq"></a>

**Why the Zapier connector is in my alert source?**

Every time you create a Zap with an ilert trigger, the Zapier connector in ilert is created automatically for the alert source you selected in the trigger.
