---
description: The ilert checkmk native integration ships with checkmk version >= 2.0.0.
---

# Checkmk Integration (v 2.0+ )

With the native ilert notification integration in Checkmk, you can automatically create alerts in ilert from Checkmk alerts. That way, you will never miss a critical alert and always alert the right person using ilert's on-call schedules, automatic escalation, and multiple alerting channels. When checkmk creates an alert, ilert will alert the on-call person through their preferred channel, including SMS, phone calls, push notifications and Slack. ilert will automatically escalate to the next person, if the alert is not acknowledged. ilert also lets you define alerting rules based on support hours and delay alerts until your support hours start.

## In ilert: create alert source <a href="#create-alarm-source" id="create-alarm-source"></a>

1. Create a new alert source in ilert

![](<../../.gitbook/assets/mk1 (1).png>)

1. Enter a name (e.g. "checkmk server") and select your desired escalation policy.
2. Select the type **checkmk** and click save.

![](<../../.gitbook/assets/iLert (22).png>)

1. An API key is generated. You will need it below when setting up the notification configuration in checkmk.

![](<../../.gitbook/assets/iLert (23).png>)

## In checkmk: configure ilert notification <a href="#configure-ilert-plugin" id="configure-ilert-plugin"></a>

1. Navigate to the **Setup** --> **Events** --> **Notifications**

![](<../../.gitbook/assets/Picture 1.png>)

1. In the **Notification configuration**, click on **Add rule**

![](<../../.gitbook/assets/Picture 2.png>)

1. In the **Notification Method** section choose ilert method. Enter enter the **API key** and click on **Save**.

![](<../../.gitbook/assets/Picture 4.png>)

## FAQ <a href="#faq" id="faq"></a>

**Which notification types are processed?**

The plugin processes the notification types `PROBLEM` , `ACKNOWLEDGEMENT` and `RECOVERY`. The remaining Notification Types (including `FLAPPING*` and `DOWNTIME*`) are ignored.

checkmk has the following alarm types:

| Types             | Description                                 |
| ----------------- | ------------------------------------------- |
| PROBLEM           | Normal host or service problem              |
| RECOVERY          | Host / service goes UP / OK again           |
| ACKNOWLEDGMENT    | Acknowledgment of a problem                 |
| FLAPPINGSTART     | A host / service begins to be discontinuous |
| FLAPPINGSTOP      | End of discontinuity                        |
| DOWNTIMESTART     | Start of scheduled maintenance.             |
| DOWNTIMEEND       | Normal end of maintenance                   |
| DOWNTIMECANCELLED | Premature termination of maintenance        |
| CUSTOM            | Alarm triggered manually by command         |
| ALERT HANDLER     | Alerthandler execution (CEE from 1.4.0i2)   |

**Will alerts in ilert be resolved automatically?**

Yes, as soon as the state of a host / service is UP or OK again in checkmk, the associated alert is resolved in ilert. If a problem is acknowledged in checkmk, the associated alert in ilert is set to the status Accepted.

**Can I link checkmk to multiple alert sources in ilert?**

Yes, create a checkmk user for each alert source in checkmk. Proceed as described above in the instructions.
