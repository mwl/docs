---
title: Github Inbound Issue Integration
seoTitle: 'iLert: Github Issue Integration for Alerting | Incident Response | Uptime'
description: Create alerts in ilert based on issues from GitHub repositories.
date: '2020-04-21T07:00:00.000Z'
weight: 1
---

# GitHub Inbound Issue Integration

With the ilert Github Issue integration, you can create alerts in ilert based on repository issues from Github.

## In ilert: Create a Github alert source <a id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click "Create new alert source"
2. Enter a name and select your desired escalation policy. Select "Github" as the **Integration Type** and click **Save**.

![](../../.gitbook/assets/ghii1.png)

1. On the next page, a Webhook URL is generated. You will need this URL below when setting up the hook in Github.

![](../../.gitbook/assets/ghii2.png)

## In Github <a id="in-github"></a>

### Create a Repository Webhook

1. Go to your Github repository and then to **Settings** --&gt; **Webhooks** and click on **Add webhook** to add a new webhook \(`https://github.com/<org>/<repo>/settings/hooks`\)

![](../../.gitbook/assets/ghii3.png)

1. In the **Payload URL** section, set the **Webhook URL** that you generated in ilert
2. In the **Content type** section, set the **application/json**

![](../../.gitbook/assets/ghii4.png)

1. In the **Which events would you like to trigger this webhook?** section, change it to **Let me select individual events** and select the **Check runs** events

![](../../.gitbook/assets/ghii5.png)

1. Click **Save**

## FAQ <a id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes, as soon as the Github issue is closed, the alert in ilert will be resolved automatically.

**Can I connect Github with multiple alert sources from ilert?**

Yes, simply create more webhooks in Github.

**Can I customize the alert messages?**

No.

