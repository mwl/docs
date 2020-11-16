---
description: >-
  Create iLert incidents from HashiCorp Consul Health Check events and get
  alerted through iLert for high priority issues.
---

# HashiCorp Consul

With the iLert HashiCorp Consul integration you can create incidents in iLert based on HashiCorp Consul Health Check events.

## In iLert <a id="in-ilert"></a>

### Create an alert source <a id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click **Create new alert source**

2. Enter a name and select your desired escalation policy. Select "API" as the **Integration Type** and click on **Save**.

![](../.gitbook/assets/ilert%20%2815%29.png)

3. On the next page, an API Key is generated. You will need this API Key below when setting up the Consul-Alerts tool.

![](../.gitbook/assets/ilert%20%2814%29.png)

## In Consul Server <a id="in-topdesk"></a>

### Configure Consul-Alerts

1. Install Consul-Alerts as per the guide at [https://github.com/AcalephStorage/consul-alerts/blob/master/README.md](https://github.com/AcalephStorage/consul-alerts/blob/master/README.md)

2. Once Consul-Alerts is running, we can configure the iLert integration key using curl.

```bash
curl -X PUT -d 'YOUR_API_KEY' http://localhost:8500/v1/kv/consul-alerts/config/notifiers/ilert/api-key
```

3. Enable iLert notifications in Consul-Alerts.

```bash
curl -X PUT -d 'true' http://localhost:8500/v1/kv/consul-alerts/config/notifiers/ilert/enabled
```

4.  \(Optional\) Generating a test incident by having a health check fail to confirm the integration is working.

## FAQ <a id="faq"></a>

**Will incidents in iLert be resolved automatically?**

Yes, Consul-Alerts will resolve the iLert incident once health checks are passing.

**Will incidents in iLert be accepted automatically?**

No, unfortunately Consul events are not compatible with iLert accepted event.

**Can I connect Consul Server with multiple alert sources from iLert?**

No, Consul-Alerts only supports sending incidents to a single alert source.
