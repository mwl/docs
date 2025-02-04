---
description: >-
  Create ilert alerts from HashiCorp Consul Health Check events and get alerted
  through ilert for high priority issues.
---

# HashiCorp Consul

| ![](<../.gitbook/assets/Consul Cloud Verified Badge\_Small (1).png>) | [HashiCorp Consul](https://www.consul.io/) is a service mesh solution providing a full featured control plane with service discovery, configuration, and segmentation functionality. This integration creates based on Consul health checks. |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

## In ilert <a href="#in-ilert" id="in-ilert"></a>

### Create an alert source <a href="#create-alert-source" id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click **Create new alert source**
2. Enter a name and select your desired escalation policy. Select "API" as the **Integration Type** and click on **Save**.

![](<../.gitbook/assets/iLert (28).png>)

1. On the next page, an API Key is generated. You will need this API Key below when setting up the Consul-Alerts tool.

![](<../.gitbook/assets/iLert (29).png>)

## In Consul Server <a href="#in-topdesk" id="in-topdesk"></a>

### Configure Consul-Alerts

1. Install Consul-Alerts as per the guide at [https://github.com/iLert/consul-alerts/blob/master/README.md](https://github.com/iLert/consul-alerts/blob/master/README.md)
2. Once the Consul-Alerts are running, we can set the ilert integration key using curl.

```bash
curl -X PUT -d 'YOUR_API_KEY' http://localhost:8500/v1/kv/consul-alerts/config/notifiers/ilert/api-key
```

1. Enable ilert notifications in Consul-Alerts.

```bash
curl -X PUT -d 'true' http://localhost:8500/v1/kv/consul-alerts/config/notifiers/ilert/enabled
```

1. (Optional) Generating a test alert by having a health check fail to confirm the integration is working.

## FAQ <a href="#faq" id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes, Consul-Alerts will resolve the ilert alert once health checks are passing.

**Will alerts in ilert be accepted automatically?**

No, unfortunately Consul events are not compatible with ilert accept events.

**Can I connect Consul Server with multiple alert sources from ilert?**

No, Consul-Alerts only supports sending alerts to a single alert source.
