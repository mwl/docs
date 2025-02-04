---
description: >-
  With the ilert Kapacitor integration, you can create alerts in ilert based on
  Kapacitor alerts.
---

# Kapacitor Integration

[Kapacitor](https://docs.influxdata.com/kapacitor/) is an open source data processing framework that makes it easy to create alerts, run ETL jobs and detect anomalies. Kapacitor is the final piece of the [TICK stack](https://influxdata.com/time-series-platform/).

## In ilert <a href="#in-ilert" id="in-ilert"></a>

### Create a Kapacitor alert source <a href="#create-alert-source" id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click **Create new alert source**

![](../.gitbook/assets/Screenshot\_16\_03\_21\_\_16\_37.png)

1. Enter a name and select your desired escalation policy. Select "Kapacitor" as the **Integration Type** and click on **Save**.

![](<../.gitbook/assets/iLert (50).png>)

1. On the next page, a Webhook URL is generated. You will need this URL below when setting up the alert rule in Kapacitor.

![](<../.gitbook/assets/iLert (51).png>)

## In Kapacitor <a href="#in-kapacitor" id="in-kapacitor"></a>

### Create an alert rule <a href="#create-alert-rule" id="create-alert-rule"></a>

1. Go to Chronograph dashboard, then to **Alert Rule** and click on the **Create Rule** button

![](../.gitbook/assets/Screenshot\_2021-03-29\_at\_15\_11\_55.png)

1. On the next page,  define your alert conditions, paste the **Webhook URL** that you generated in ilert, define alert summary and click on the **Save Rule** button

![](../.gitbook/assets/Chronograf.png)

Finished! Your Kapacitor alerts will now create alerts in ilert.

## FAQ <a href="#faq" id="faq"></a>

**Will alerts in ilert be resolved automatically?**

Yes, as soon as an alert has been completed in Kapacitor, the associated alert in ilert will be resolved automatically.

**Can I connect Kapacitor with multiple alert sources from ilert?**

Yes, simply add more alert rules in Kapacitor.
