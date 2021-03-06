# Function Compute {#concept_zbp_mc2_zdb .concept}

By monitoring multiple metrics of Function Compute, such as the service-level and function-level TotalInvocations, average Duration, and distribution of request status, CloudMonitor helps you to monitor the running status of Function Compute. CloudMonitor automatically collects data forFunction Compute metrics from the time after you purchase the Function Compute service.

## Monitoring service {#section_zqh_pd2_zdb .section}

-   **Metrics**

    |Metric|Dimension|Unit|Minimum monitor granularity|
    |:-----|:--------|:---|:--------------------------|
    |Billableinvocations|User, service, and function|Count|1 minute|
    |BillableInvocationsRate|User, service, and function|Percent|1 minute|
    |ClientErrors|User, service, and function|Count|1 minute|
    |ClientErrorsRate|User, service, and function|Percent|1 minute|
    |ServerErrors|User, service, and function|Count|1 minute|
    |ServerErrorsRate|User, service, and function|Percent|1 minute|
    |Throttles|User, service, and function|Count|1 minute|
    |ThrottlesRate|User, service, and function|Percent|1 minute|
    |Totalinvocations|User, service, and function|Count|1 minute|
    |Average duration|User, service, and function|Millisecond|1 minute|

    **Note:** 

    -   Monitoring data is saved for up to 31 days.
    -   You can view the monitoring data for up to 14 consecutive days.

-   **View monitoring data.**
    1.  Log on to the [CloudMonitor Console](https://cms-intl.console.aliyun.com).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Function Compute**.
    3.  Click **Service List** to view the monitoring information on the Service or Function level.

## Alarm service {#section_av5_bf2_zdb .section}

CloudMonitor provides alarm functions for Function Compute metrics, so you are notified immediately in case of any metric exceptions.

-   **Set an alarm rule.**
    1.  Log on to the [CloudMonitor Console](https://cms-intl.console.aliyun.com).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Function Compute**.
    3.  In the **Service** or **Function** list, click **Monitoring Chart** in the **Action** column to access the monitoring details page.
    4.  Click the bell icon in the upper-right corner of the monitoring chart or **New Alarm Rule** in the upper-right corner of the page to set an alarm rule for corresponding monitoring metrics of this instance.

-   **Set multiple alarm rules.**
    1.  Log on to the [CloudMonitor Console](https://cms-intl.console.aliyun.com).
    2.  In the left-side navigation pane, choose **Cloud Service Monitoring** \> **Function Compute**.
    3.  Click **Alarm Rules** to go to the  **Alarm Rules** list page. Click **Create** in the upper-right corner to create alarm rules.
-   **Parameters**
    -   **Products**: ECS, RDS, OSS, among others
    -   **Resource Range**: the range for which an alarm rule takes effect. There are two alarm rule ranges available: **All Resources** and **Instances**.
        -   **All Resources**: Indicates that the specified alarm rule applies to all Function Compute instances under your name. For example, if you set the resource range to all resources, and set the alarm threshold for CPU usage to 80%, then an alarm is triggered when the CPU usage of any Function Compute instance exceeds 80%. When you select **All Resources**, you can report alarms for up to 1,000 resources. If the number of your resources exceeds 1,000, alarms cannot be reported for some resources even if they exceed the threshold you set in your alarm rule. Therefore, for these scenarios, we recommend that you use application groups to divide resources by service before setting up alarm rules to avoid this issue.
        -   **Instances**: Indicates that the specified rule only applies to a specific instance. For example, if you set the resource range to **Instances** and set the alarm threshold for CPU usage to 80%, an alarm is triggered when the CPU usage of the specified instance exceeds 80%.
    -   **Alarm Rule**: the alarm rule name
    -   **Rule Describe**: the main content of the alarm rule where you define the alarm-triggering conditions, or value threshold, for related metrics. For example, if you describe the rule as **1mins Maximum Memory Usage Value \>= 1024 MBytes**, the alarm service will check every minute whether the maximum memory usage value within one minute meets or exceeds 1024 MBytes.

        Consider the following example. For the alarm service in host monitoring, one data point is reported in 15 seconds for a single server metric, and 20 data points in five minutes. This relates to the following alarm rules.

        -   **5mins Average CPU Usage \> 90%**: The average CPU usage value of the 20 data points in five minutes exceeds 90%.
        -   **5mins CPU Usage Always \> 90%**: The CPU usage values of the 20 data points in five minutes all exceed 90%.
        -   **5mins CPU Usage Once \> 90%**: The CPU usage value of at least one of the 20 data points in five minutes exceeds 90%.
        -   **Total 5mins Internet Outbound Traffic \> 50 MB**: The sum of the outbound traffic values of the 20 data points in five minutes exceeds 50 MB.
    -   **Mute For**: the period of time that an alarm is muted so that alarm contacts do not receive any alarm notifications during this period. An alarm rule can be muted for up to 24 hours \(or 1 day\).
    -   **Triggered when threshold is exceeded for**: An alarm notification is sent if the detected values reach the alarm rule threshold a certain number of times consecutively.
    -   **Effective Period**: the period of time for which an alarm rule is effective. During this period of time, the alarm service checks metric data and determines whether to generate an alarm.
    -   **Notification Contact**: a group of contacts who receive alarm notifications.
    -   **Notification Methods**: Emails and DingTalk chatbot.
    -   **Email Subject**: The email subject is set as the product name, metric, and instance ID involved in the alarm by default.
    -   **Email Remark**: supplementary information customized for an alarm email. Remarks are sent as part of the alarm notification email body.
    -    **HTTP CallBack**: Enter a URL accessible through the Internet and CloudMonitor will push the alarm information to the address through a POST request. Currently, only HTTP is supported.

