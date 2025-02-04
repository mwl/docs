---
title: Instana Integration
seoTitle: 'iLert: Instana Integration for Alerting | Incident Response | Uptime'
date: '2018-12-29T05:02:05.000Z'
weight: 1
description: The ilert Instana Integration helps you to easily connect ilert with Instana.
---

# Instana Integration

[Instana](https://www.instana.com/) is an application performance monitoring software for microservice applications. With the ilert Instana Integration, you can receive Instana alerts through ilert and easily extend Instana with SMS, Push, Voice, and ilert on-call-scheduling.

## In ilert: Create Instana alert source <a href="#create-alarm-source" id="create-alarm-source"></a>

1. Go to the **Alert sources** tab and click on **Create new alert source**
2. Enter a name and select your desired escalation policy
3. Select "Instana" as the **Integration type**

![](<../.gitbook/assets/i1-1 (1).png>)

1. The URL shown on the next page is the HTTP endpoint for the Webhook in Instana and will be needed below.

![](../.gitbook/assets/i1-2.png)

## In Instana: Create webhook integration <a href="#create-webhook-integration" id="create-webhook-integration"></a>

1. \_\*\*\_Open the Management Portal by clicking on Profile → Management Portal
2. Go to the **Integration** tab and click on **WEBHOOK**.

![](../.gitbook/assets/i1-3.png)

1. In the **Notify on** field, select the event types for which you want alerts from ilert.
2. In the **Webhook URL** field, copy the URL from the alert source set up in ilert and click on **Save**.

## FAQ <a href="#faq" id="faq"></a>

**Will alerts in ilert be resolved automatically?**

For alerts and issues in Instana: Yes, as soon as the state of an alert or issue is CLOSED in Instana, the alert in ilert will be resolved.

For Change and On / Offline Events: Every Change and On / Offline event generates a new Alert in ilert.
