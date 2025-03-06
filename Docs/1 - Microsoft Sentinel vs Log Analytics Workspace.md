# Log Analytics Workspace

* Log Analytics Workspace is a storage solution from Azure that is used to store 'logs' in a structured JSON format

* It can be compared to a 'database' where the logs are stored in the form of tables

* Each log is ingested and stored in a table in a Log Analytics Workspace

* A Log Analytics Workspace has 'default' tables - that are created, and managed by Microsoft for approved and recognized log sources from Microsoft. Example: SigninLogs, DeviceEvents, SecurityAlert, AzureDiagnostics, etc.

* A Log Analytics Workspace can have 'custom' tables - that can be created by users and organisations to ingest data from third-party log sources that are not natively supported by Microsoft. Example: CortexXDRIncidents_CL, Okta_CL, CrowdStrikeEndpointIncidents_CL, etc.

* The names of the custom tables will have to end with the suffix '_CL' - which helps differentiate a default table from a custom table. 'CL' stands for 'Custom Log'

> In summary - Log Analytics Workspace is basically a database

<br>

# Microsoft Sentinel

* Microsoft Sentinel is a SIEM and SOAR platform

* Microsoft Sentinel by itself DOES NOT have any form of log storage

* Microsoft Sentinel uses 'Log Analytics Workspace' as the database to store the logs

* Microsoft Sentinel brings in the following capabilities to utilize the logs stored in Log Analytics Workspace - to make meaningful content out of the raw logs,
    * Data Connectors - a component to enable the log collection from log sources
    * Analytic Rules - to detect any suspicious or malicious activities from the raw logs
    * Workbook - to visualize the logs in a graphical representation (pretty pictures)
    * Automation Rules - to perform a basic action automatically over an incident based on the provided conditions
    * Playbooks (Logic Apps) - to perform a complex action automatically over an incident based on provided logic and conditions

> In summary - Microsoft Sentinel is just an application that sits on top of Log Analytics Workspace to run a SIEM and SOAR platform

<br>

# Conclusion

Microsoft Sentinel and Log Analytics Workspace are tightly bound with each other - making them function together as a SIEM and SOAR solution. Since they are tightly bound, people often use the word 'Sentinel' instead of using the word 'Log Analytics Workspace'. Example: we often refer the logs and tables stored in Log Analytics Workspace as 'Sentinel logs' or 'Sentinel tables'. But Sentinel doesn't have the capability to store logs or tables. It has to use a Log Analytics Workspace to store the logs and tables.

It is usually due to the laziness to spell out 'Log Analytics Workspace' every single time. Instead spelling out 'Sentinel' is much shorter and easier to refer. Regardless of the implicit meaning - it is necessary to understand the underlying infrastructure and the relation between the two platforms.