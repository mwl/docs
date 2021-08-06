---
description: The iLert Zendesk Integration helps you to easily connect iLert with Zendesk.
---

# Zendesk Outbound Integration

[Zendesk](https://www.zendesk.com/) is a cloud-based help desk management solution offering customizable tools to build customer service portal, knowledge base and online communities.

## In Zendesk: Create API Token <a id="api-token"></a>

1. Optional: create a dedicated iLert user in Zendesk. That way, you will be able to distinguish tickets created by iLert.

{% hint style="warning" %}
**Admin permission required**

To set up the integration, the Zendesk user must have agent permissions.
{% endhint %}

2. Go to admin settings, select the API channel, enable token access and create an API token. 

![](../../.gitbook/assets/zd1.png)

3. You will need this API token later in iLert. Make sure to copy and store it. You won't be able to see it again in Zendesk. Click **Save**.

## In iLert: create a Zendesk connector and link it with an alert source <a id="alarm-source"></a>

{% hint style="info" %}
**Admin permission required**

To set up the integration, you must have admin rights in iLert.
{% endhint %}

1. ****Click the gear icon and then click on the **Connectors** link

![](../../.gitbook/assets/screenshot_16_03_21__15_46.png)

2. Click the **Add Connector** button

![](../../.gitbook/assets/screenshot_16_03_21__15_48.png)

3. On the next page, choose **Zendesk Support** as type, name the connector, enter your zendesk URL in the form **https://{your-domain}.zendesk.com**, enter your Zendesk user **Email** and **API-Key** that you generated before **** and click on the save button

![](../../.gitbook/assets/ilert%20%2895%29.png)

4. Go to **Alert sources** and select the alert source you want to connect with Zendesk. Click on **Incident Actions → Add new incident action**.

![](../../.gitbook/assets/ilert%20%2892%29.png)

5. On the next page choose **Zendesk Support** as the type, choose the connector created in step 3, name it, choose **Priority** of the Zendesk tickets and click on the **Save** button.

![](../../.gitbook/assets/ilert%20%2891%29.png)

6. You're done! You can now test this connection by clicking on **Test this connection**. A test ticket will be created in Zendesk.

![](../../.gitbook/assets/ilert%20%2893%29.png)

## FAQ <a id="faq"></a>

**Are tickets updated in Zendesk if the incident is updated in iLert?**

Yes, status updates to iLert Incidents are reflected in the title of the Zendesk ticket, e.g. `RESOLVED` host compute.infra is `DOWN`.

**Can I choose which updates to publish to a ticket in Zendesk?**

Currently not. If that's something you'd like see in iLert, we look forward to your feedback via chat or e-mail.
