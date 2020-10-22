---
description: >-
  This page contains release notes for new features and improvements released
  after April, 2020.
---

# iLert Release Notes

## October 2020

### New features

* Added new [Responder role](getting-started/user-roles-and-permissions.md#responder).

### New and updated integrations

* Sysdig Inbound and Outbound Integration

### Improvements

* Call routing: added mailbox transcription to incident details and made voicemail links easier accessible in the incident links section

## September 2020

### New features

* Incident Actions
* Support for outbound connections in Call Routing Numbers
* Support Hours for Call Routing Numbers

### New and updated integrations

* [Email Outbound Integration](integrations/email-outbound-integration.md)
* [Kentix AlarmManager](integrations/kentix-am.md)
* Datadog Outbound Integration now supports regions
* Prometheus incident detail formatting has been updated
* Slack channels \(connections\) can now be managed in iLert directly

### Improvements

* Ability to select incident events in outbound integrations. Example: trigger webhooks for incident creation and resolution events, but ignore remaining incident event types.
* Every call routing number is now referenced to an alert source, helping you connect incoming calls to e.g. Slack. You can now also manage support hours for your call routing number.
* Optimized bulk incident actions like accept and resolve
* Uptime monitor TCP and UDP modes now support first packet and expected packet
* Further improvements on our API to optimize response time and delivery for our mobile app
* New API endpoint /numbers

## August 2020

### New features

* Ability to re-route incidents to escalation policies and on-call schedules
* Suggested responders: when re-routing an incident, iLert now suggests you the best responder based on historic data

### New and updated integrations

* [Autotask](integrations/autotask.md)
* [Zabbix](integrations/zabbix/native.md) \(updated\): Starting Zabbix 4.4, iLert can be integrated as a media type into Zabbix. Zabbix 5.0.4+ includes iLert as a media type by default. See also Zabbix blog post: [Working with multiple on-call teams using Zabbix and iLert](https://blog.zabbix.com/working-with-multiple-on-call-teams-using-zabbix-and-ilert/11847/) 
* [Prometheus](integrations/prometheus.md) \(updated\): improved readabiltiy of prometheus incidents

### Improvements

* Alert source overview page now includes outbound connections
* User profile: low priority notifications rules are entirely optional, i.e. a user can now chose to not receive any notification for low priority incidents

## July 2020

### New Features

* [Heartbeat Monitoring](uptime-monitors/heartbeat-monitoring/)

## June 2020

### Updated integrations

* [Email](integrations/email/): added ability to resolve incidents via email

### Improvements

* [Stakeholder engagement](getting-started/stakeholder-engagement.md): stakeholders can now unsubscribe from incident update notifications
* Email login: Users can now login via email \(in addition to username\) . Usernames in iLert are deprecated and will be removed in the future.

## May 2020

### New features

* [Stakeholder engagement](getting-started/stakeholder-engagement.md): keep stakeholders in the loop during critical incidents \([blog post](https://www.ilert.com/blog/2020-05-27-stakeholder-engagement-release-notes/)\).

### New and updated integrations

* [AWS Personal Health Dashboard](integrations/aws-phd.md)
* [StatusCake](integrations/statuscake.md)
* Serverless outbound integrations:
  * [AWS Lambda](integrations/aws-lambda.md)
  * [Google Cloud Functions](integrations/gcf.md)
  * [Microsoft Azure Functions](integrations/azure-functions.md)
* [Icinga v2.x](integrations/icinga.md) \(updated\): there is a dedicated plugin for Icinga now on our [GitHub repo](https://github.com/iLert/ilert-icinga). You can now override the incident priority from within Icinga and we include the comments that you enter in Icinga when ack’ing a problem in the event log of the incident.
* [JIRA](integrations/jira.md) \(updated\): When you setup a connection from your alert source in iLert to your JIRA instance, projects and issue types are now dynamically fetched from your JIRA instance, so you can select the issue types when iLert syncs an incident to JIRA. You can even include custom fields.
* [Webhook](integrations/webhook.md) \(updated\): you can now fully customize the payload for outbound webhooks.

### Improvements

* [API end point](https://api.ilert.com/api-docs/#tag/Uptime-Monitors) for uptime monitors
* Uptime monitors: support for milliseconds in check timeout \([blog post](https://www.ilert.com/blog/2020-05-27-stakeholder-engagement-release-notes/#uptime-monitoring)\)
* Flexible periods in repeating on-call schedules: set an arbitrary period length and chose between days and weeks as the period unit \([blog post](https://www.ilert.com/blog/2020-05-27-stakeholder-engagement-release-notes/#flexible-periods)\)

## April 2020

### New features

* [Single Sign On](integrations/sso.md): Single sign on makes it easy to manage access to your iLert account using an identity provider of your choice.
* **Incident Reporting** includes key metrics such MTTA and MTTR \([blog post](https://www.ilert.com/blog/2020-04-07-incident-reports-ilert-sso/#reports)\).

### New integrations

* [AppDynamics](integrations/appdynamics.md)
* [TopDesk](integrations/topdesk/)
* [Discord](integrations/discord.md)
* [GitHub](integrations/github/)
* [Dynatrace](integrations/dynatrace.md)

### Improvements

* **Auto raise incident priority** lets you delay notifications and escalations until support hours start \([blog post](https://www.ilert.com/blog/2020-04-07-incident-reports-ilert-sso/#auto-raise)\)


