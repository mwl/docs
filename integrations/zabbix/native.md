---
title: Zabbix Native Integration
seoTitle: 'iLert: Zabbix Integration for Alerting | Incident Response | Uptime'
description: The iLert Zabbix Integration helps you to easily connect iLert with Zabbix.
date: '2020-07-02T08:02:05.000Z'
weight: 1
---

# Zabbix Native Integration

## System Requirements <a id="requirements"></a>

* Zabbix 4.4+

## In iLert: Create alert source <a id="create-alarm-source"></a>

1. Go to **Alert sources** and click on **Add a new alert source**.

![](../../.gitbook/assets/zbn1.png)

1. Set a name \(e.g. "Zabbix"\) and select your desired escalation policy.
2. Set the **Integration type** to Zabbix.

![](../../.gitbook/assets/zbn2.png)

1. An API key is generated on the next page. You will need the API key below when setting up the media type in Zabbix.

![](../../.gitbook/assets/zbn3.png)

## In Zabbix <a id="zabbix"></a>

### Import iLert media type \(if needed\)

1. Download the iLert Zabbix Media Type file: [https://raw.githubusercontent.com/iLert/ilert-zabbix/master/media\_ilert.xml](https://raw.githubusercontent.com/iLert/ilert-zabbix/master/media_ilert.xml)
2. Go to the **Administration → Media types** tab and click the **Import** button.

![](../../.gitbook/assets/zbn4.png)

1. Select Import file [media\_ilert.xml](https://github.com/iLert/docs/tree/a6ca40eea91b6e1c9a00c47229f767d9f1e0b7b8/integrations/zabbix/media_ilert.xml) and click the **Import** button at the bottom to import the iLert media type.

![](../../.gitbook/assets/zbn5.png)

1. Set the **.ILERT.ALERT.SOURCE.KEY** variable to the alert source api key that you generated in iLert
2. Optional: you can rewrite standard incident summary with custom template via **.ILERT.INCIDENT.SUMMARY** variable e.g. `{TRIGGER.NAME}: {TRIGGER.STATUS} for {HOST.HOST}`

![](../../.gitbook/assets/zbn6.png)

1. Click the **Update** button to save the media type.

### Create iLert user and group

1. Go to the **Administration → User groups** tab and click the **Create user group** button.

![](../../.gitbook/assets/zbn7.png)

1. Set the name for the iLert group \(eg "iLert group"\).

![](../../.gitbook/assets/zbn8.png)

1. Switch to the **Permissions** tab and select the **host groups** that the iLert group should have read access to send notifications. Without read access, iLert cannot receive notifications for the hosts in the group \(see also [here](https://www.zabbix.com/documentation/4.4/manual/quickstart/notification)\).
2. Click the Add button to save the group.

![](../../.gitbook/assets/zbn9.png)

1. Switch to the Users tab and click the **Create user** button.

![](../../.gitbook/assets/zbn10.png)

1. Assign **alias** and **name** and add the user to the iLert group. No further details such as password are necessary as this user will not log in to Zabbix.

![](../../.gitbook/assets/zbn11.png)

1. Switch to the **Media** tab and click the **Add** link
2. In the **media** window, select iLert as **Type** , enter any text, as this value is not used, but is required in the **Send to** field and click the **Add** button

![](../../.gitbook/assets/zbn12.png)

1. Click the **Add** button in the **Users** tab to save the user.

![](../../.gitbook/assets/zbn13.png)

### Create alert action

1. Switch to the **Configuration → Actions** tab and click the **Create action** button

![](../../.gitbook/assets/zbn14.png)

1. Give the action a name, eg "iLert notifications".

![](../../.gitbook/assets/zbn15.png)

1. Perform the following actions on the **Operations**, **Recovery operations** and **Acknowledgment operations** tabs

![](../../.gitbook/assets/zbn16.png)

1. Change the default subject and default message if you want.
2. Click on the New link under Operations and select the **iLert** group created above under Send to User groups.

![](../../.gitbook/assets/zbn17.png)

1. Click the **Add** button to save the action

## FAQ <a id="faq"></a>

**Are incidents automatically resolved in iLert?**

Yes, as soon as the status of an incident is OK in Zabbix, the associated incident is resolved in iLert.

**Can I link Zabbix to multiple alert sources in iLert?**

Yes, create several **iLert users** in Zabbix and store the corresponding **API key** in the **media type**.

**What if my internet connection is lost? Are the events generated in Zabbix lost?**

No events are lost. The zabbix server tries to send the events to iLert every 30 seconds with 10 attempts \(can be configured in media type settings\). As soon as your connection is available again, all events are sent to iLert. We also recommend that you monitor your Internet connection with an external monitoring service. You can then send these alerts to iLert.

**The plugin does not work. How do I find the mistake?**

Please look first in the **Problems View** in Zabbix under actions column. If you can not find the error, please contact our support at [support@ilert.com](mailto:support@ilert.com).
