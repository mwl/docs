---
description: >-
  The ilert Server Density Integration helps you to easily connect ilert with
  Server Density.
---

# Server Density

With the ilert Server Density integration you can create alerts in ilert based on Server Density notifications.

## In ilert <a href="#in-ilert" id="in-ilert"></a>

### Create a Server Density alert source <a href="#create-alert-source" id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click **Create new alert source**
2. Enter a name and select your desired escalation policy. Select "Server Density" as the **Integration Type** and click on **Save**.

![](<../.gitbook/assets/iLert (10).png>)

1. On the next page, a Webhook URL is generated. You will need this URL below when setting up the Webhook in Server Density.

![](<../.gitbook/assets/iLert (11).png>)

## In Server Density <a href="#in-topdesk" id="in-topdesk"></a>

### Create notification channel <a href="#create-action-sequences" id="create-action-sequences"></a>

1. Go to Server Density and then to **Settings.** Click on **Notifications** to add a new notification channel for ilert

![](../.gitbook/assets/Preferences\_-\_Server\_Density.png)

1. In section **Type** choose **Webhook**.
2. In the **Name** section, enter a name eg. `iLert`
3. In the section **URL** field, paste the **Webhook URL** that you generated in ilert

![](../.gitbook/assets/Preferences\_-\_Server\_Density\_and\_Passwords.png)

1. In the **Channel Name** section, enter a name eg. `iLert`
2. Click on **+** (plus) button

### Configure an alert for a service or device <a href="#create-action-sequences" id="create-action-sequences"></a>

1. Go to **Services** or **Devices** and choose the one that interests you**.** Click on the **Alerting tab**
2. Create an alert or use an existing one
3. Click on the **alert action** that interests you
4. Choose "iLert" under **Trigger webhook** group

![](../.gitbook/assets/My\_Website\_-\_Server\_Density.png)

## FAQ <a href="#faq" id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes

**Will alerts in ilert be accepted automatically?**

No, unfortunately Server Density's notification is not compatible with ilert's accepted event.

**Can I connect Server Density with multiple alert sources from ilert?**

Yes, simply create more notification channels in Server Density.
