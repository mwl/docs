---
title: Github Inbound Check Run (Actions) Integration
seoTitle: 'iLert: Github Actions Integration for Alerting | Incident Response | Uptime'
description: Create alerts in ilert based on Check runs from GitHub.
date: '2020-04-21T07:00:00.000Z'
weight: 1
---

# GitHub Inbound Check Run \(Actions\) Integration

With the ilert Github Check Run integration, you can add alerts in ilert based on "check run" from Github \(e.g. Github Actions\).

## In ilert: Create Github alert source <a id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click "Create new alert source"
2. Enter a name and select your desired escalation policy. Select "Github" as **Integration Type** and click **Save**.

![](../../.gitbook/assets/ghch1.png)

1. On the next page, a Webhook URL is generated. You will need this URL below when setting up in Github.

![](../../.gitbook/assets/ghch2.png)

## In Github <a id="in-github"></a>

### Create a Repository Webhook

1. Go to your Github repository and then to **Settings** --&gt; **Webhooks** and click on **Add webhook** to add a new webhook \(`https://github.com/<org>/<repo>/settings/hooks`\)

![](../../.gitbook/assets/ghch3.png)

1. In the **Payload URL** section, set it to the **Webhook URL** generated in ilert
2. In the **Content type** section, change to **application/json**
3. In the **Which events would you like to trigger this webhook?** section, change it to **Let me select individual events** and select the **Check runs** events

![](../../.gitbook/assets/ghch4.png)

1. Click **Save**

## FAQ <a id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes, as soon as the recovery conditions of check run are met, the alert in ilert will be resolved automatically.

**Can I connect Github with multiple alert sources from ilert?**

Yes, simply create more webhooks in Github.

**Can I customize the alert messages?**

No.

