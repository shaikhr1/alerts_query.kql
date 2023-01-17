# alerts_query.kql
Here's a sample KQL (Kusto Query Language) query that you can use to retrieve information about recent alerts in Microsoft Sentinel
This query retrieves the last 10 alerts generated within the last 7 days.
You can customize the query by adjusting the time range or the number of alerts retrieved by using the $top parameter in your query.
You can also filter the alerts by adding conditions to the where clause like severity, type, or source.

You can use this query in the Microsoft Sentinel Advanced hunting by pasting the query in the KQL editor.

You can also check the KQL documentation for more information on Kusto Query Language https://docs.microsoft.com/en-us/azure/kusto/query/

Please note that you need an Azure tenant, and a Microsoft Sentinel subscription to access the Advanced hunting feature and to be able to run the queries.


let start = ago(7d);
let end = now();
Alerts
| where TimeGenerated >= start and TimeGenerated <= end
| take 10
