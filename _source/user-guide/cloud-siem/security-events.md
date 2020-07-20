---
layout: article
title: Investigate security events
permalink: /user-guide/cloud-siem/security-events.html
flags:
  logzio-plan: enterprise
tags:
  - logz.io-security
  - siem
contributors:
  - shalper
---

Cloud SIEM logs a security event every time a security rule triggers in your Security account. The terms **triggered rules** and **security events** have the same meaning and  are used interchangeably.

The event log includes details about the security incident and the rule that caused it to trigger. It also offers a button **Investigate** to quickly pull up the logs to be investigated directly in Kibana Discover.

### Fields of interest

|---|---|
| type: logzio-alerts | All security event logs belong to this log type. |
| sub-type: security_rule | All security event logs belong to this sub-type. |
| logzio-alert-definition-id | Every security rule in Logz.io Cloud SIEM has a unique identifier. The identifier can be used to aggregate all events triggered by the same rule. |
| logzio-hits | The number of logs involved in the security event. This is the number of logs that triggered the security rule before applying any aggregations, if applicable. |
| logzio-investigate | Click the **Investigate** button to pull up the logs responsible for triggering the rule in Kibana Discover. The appropriate filters and search query are applied to returns only the relevant logs. Notice the number of **hits** in Kibana Discover matches the number in the event log. |
{:.paramlist}


### Log retention concerns

Logs of security events, that is logs of triggered rules, are kept for 10 years. This ensures that details concerning security incidents are kept on record and can be investigated and re-visited many months and even years after the fact, as new findings come to light.

When you click the **Investigate** button for an event, you are pulling up logs from your short-term logging account. The availability of these logs depends on the retention plan in your Log Analytics account.

Log retention typically spans between 3-30 days. If you are an admin of the Main logging account, you can look up the retention policy on the [Manage accounts](https://app.logz.io/#/dashboard/settings/manage-accounts) page.

### Investigate expired logs

If you would like to investigate logs after they have expired from the logging database, you have the following options:

1. Set up [archiving](/user-guide/archive-and-restore/). Once logs are no longer in retention, they can be resored from archive.

2. Set up [Optimizers](/user-guide/optimizers/configure-optimizers.html) to capture logs and save them to a [Timeless account](/user-guide/accounts/manage-timeless-accounts.html).
