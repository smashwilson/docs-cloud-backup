
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

List All Backup Configurations For An Agent
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v1.0/{tenant_id}/backup-configuration/system/{machineAgentId}

Lists the backup configurations for the specified agent.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |The request succeeded.   |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |There were one or more   |
|                          |                         |errors in the request.   |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |The supplied token was   |
|                          |                         |not authorized to access |
|                          |                         |the resources. Either it |
|                          |                         |is expired or invalid.   |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Access to the requested  |
|                          |                         |resource was denied.     |
+--------------------------+-------------------------+-------------------------+
|404                       |Not Found                |The backend services did |
|                          |                         |not find anything        |
|                          |                         |matching the request URI.|
+--------------------------+-------------------------+-------------------------+
|500                       |Instance Fault           |This is a generic server |
|                          |                         |error. The message       |
|                          |                         |contains the reason for  |
|                          |                         |the error. This error    |
|                          |                         |could wrap several error |
|                          |                         |messages.                |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |This is a generic server |
|                          |                         |error. The message       |
|                          |                         |contains the reason for  |
|                          |                         |the error. This error    |
|                          |                         |could wrap several error |
|                          |                         |messages.                |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |xsd:string               |The unique identifier of |
|                          |                         |the tenant or account.   |
+--------------------------+-------------------------+-------------------------+
|{machingAgentId}          |xsd:integer              |The unique identifier of |
|                          |                         |the Cloud Backup agent.  |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example List All Backup Configurations For An Agent: JSON request**


.. code::

    GET https://dfw.backup.api.rackspacecloud.com/v1.0/1234/backup-configuration/system/224193
    User-Agent: controlpanel.drivesrvr.com
    Host: dfw.backup.api.rackspacecloud.com
    Content-Type: application/json;
    Content-Length: 0
    X-Auth-Token: 95b1788906f74d279d03001c6a14f3fe
    


Response
""""""""""""""""


This table shows the body parameters for the response:

+-----------------------------+------------------------+-----------------------+
|Name                         |Type                    |Description            |
+=============================+========================+=======================+
|BackupConfigurationId        |                        |Autogenerated ID that  |
|                             |                        |uniquely identifies a  |
|                             |                        |backup configuration.  |
|                             |                        |This ID is required on |
|                             |                        |subsequent             |
|                             |                        |GET/UPDATE/DELETE      |
|                             |                        |calls.                 |
+-----------------------------+------------------------+-----------------------+
|MachineAgentId               |                        |ID that uniquely       |
|                             |                        |identifies a Cloud     |
|                             |                        |Backup agent.          |
+-----------------------------+------------------------+-----------------------+
|MachineName                  |                        |Name of the Cloud      |
|                             |                        |Server where the Cloud |
|                             |                        |Backup agent resides.  |
+-----------------------------+------------------------+-----------------------+
|Flavor                       |                        |RaxCloudServer - for   |
|                             |                        |Rackspace Cloud        |
|                             |                        |Servers.               |
+-----------------------------+------------------------+-----------------------+
|IsEncrypted                  |                        |Indicates if backups   |
|                             |                        |are encrypted. Valid   |
|                             |                        |values are true or     |
|                             |                        |false.                 |
+-----------------------------+------------------------+-----------------------+
|BackupConfigurationName      |                        |The name of the backup |
|                             |                        |configuration. The     |
|                             |                        |configuration          |
|                             |                        |typically has the      |
|                             |                        |backup schedule, files |
|                             |                        |to backup, and         |
|                             |                        |notification options.  |
+-----------------------------+------------------------+-----------------------+
|IsActive                     |                        |Indicates if a backup  |
|                             |                        |configuration is       |
|                             |                        |active. Valid values   |
|                             |                        |are true or false.     |
+-----------------------------+------------------------+-----------------------+
|IsDeleted                    |                        |Indicates if the       |
|                             |                        |backup configuration   |
|                             |                        |is deleted. Valid      |
|                             |                        |values are true or     |
|                             |                        |false.                 |
+-----------------------------+------------------------+-----------------------+
|VersionRetention             |                        |Indicates how many     |
|                             |                        |days backup revisions  |
|                             |                        |are maintained. Valid  |
|                             |                        |values are 0, 30 , and |
|                             |                        |60. 0 means indefinite.|
+-----------------------------+------------------------+-----------------------+
|BackupConfigurationScheduled |                        |Uniquely identifies    |
|                             |                        |the schedule that is   |
|                             |                        |associated with this   |
|                             |                        |configuration.         |
+-----------------------------+------------------------+-----------------------+
|MissedBackupActionId         |                        |Specifies when to send |
|                             |                        |notification. Valid    |
|                             |                        |values are as follows: |
|                             |                        |1 that indicates that  |
|                             |                        |notifications are sent |
|                             |                        |as soon as possible,   |
|                             |                        |or 2 that indicates    |
|                             |                        |that notifications are |
|                             |                        |sent at the next       |
|                             |                        |scheduled time.        |
+-----------------------------+------------------------+-----------------------+
|Frequency                    |                        |Frequency of backup    |
|                             |                        |schedule. Valid values |
|                             |                        |are "Manually",        |
|                             |                        |"Hourly", "Daily", and |
|                             |                        |"Weekly".              |
+-----------------------------+------------------------+-----------------------+
|StartTimeHour                |                        |Indicates the hour     |
|                             |                        |when the backup runs.  |
|                             |                        |Valid values are 1     |
|                             |                        |through 12, as well as |
|                             |                        |null when the          |
|                             |                        |Frequency value is     |
|                             |                        |"Manually" or "Hourly".|
+-----------------------------+------------------------+-----------------------+
|StartTimeMinute              |                        |Indicates the minute   |
|                             |                        |when the backup runs.  |
|                             |                        |Valid values are 0     |
|                             |                        |through 59, as well as |
|                             |                        |null when the          |
|                             |                        |Frequency value is     |
|                             |                        |"Manually" or "Hourly".|
+-----------------------------+------------------------+-----------------------+
|StartTimeAmPm                |                        |Indicates AM or PM.    |
|                             |                        |Valid values are "AM"  |
|                             |                        |or "PM", as well as    |
|                             |                        |null when the          |
|                             |                        |Frequency value is     |
|                             |                        |"Manually" or "Hourly".|
+-----------------------------+------------------------+-----------------------+
|DayOfWeekId                  |                        |Indicates the day of   |
|                             |                        |the week. Valid values |
|                             |                        |are 0 through 6, with  |
|                             |                        |0 representing Sunday  |
|                             |                        |and 6 representing     |
|                             |                        |Saturday. null is also |
|                             |                        |a valid value when the |
|                             |                        |Frequency value is     |
|                             |                        |"Manually" ,"Hourly",  |
|                             |                        |or "Daily".            |
+-----------------------------+------------------------+-----------------------+
|HourInterval                 |                        |Indicates the hour.    |
|                             |                        |Valid values are 1     |
|                             |                        |through 23, as well as |
|                             |                        |null when the          |
|                             |                        |Frequency value is     |
|                             |                        |"Manually" ,"Daily",   |
|                             |                        |or "Weekly".           |
+-----------------------------+------------------------+-----------------------+
|TimeZoneId                   |                        |Specifies the time     |
|                             |                        |zone where the backup  |
|                             |                        |runs, for example      |
|                             |                        |"Eastern Standard      |
|                             |                        |Time".                 |
+-----------------------------+------------------------+-----------------------+
|NextScheduledRunTime         |                        |Specifies the next     |
|                             |                        |scheduled run time for |
|                             |                        |a backup.              |
+-----------------------------+------------------------+-----------------------+
|LastRunTime                  |                        |Indicates the last     |
|                             |                        |time a backup ran.     |
+-----------------------------+------------------------+-----------------------+
|LastRunBackupReportId        |                        |If the backup ran      |
|                             |                        |successfully last      |
|                             |                        |time, indicates the ID |
|                             |                        |of the backup report.  |
+-----------------------------+------------------------+-----------------------+
|NotifyRecipients             |                        |Indicates the email    |
|                             |                        |address to notify in   |
|                             |                        |case of backup success |
|                             |                        |or failure.            |
+-----------------------------+------------------------+-----------------------+
|NotifySuccess                |                        |Indicates if emails    |
|                             |                        |are sent after a       |
|                             |                        |successful backup.     |
|                             |                        |Valid values are true  |
|                             |                        |or false.              |
+-----------------------------+------------------------+-----------------------+
|NotifyFailure                |                        |Indicates if emails    |
|                             |                        |are sent after a       |
|                             |                        |failed backup. Valid   |
|                             |                        |values are true or     |
|                             |                        |false.                 |
+-----------------------------+------------------------+-----------------------+
|Inclusions                   |                        |Indicates the list of  |
|                             |                        |files and folders to   |
|                             |                        |back up.               |
+-----------------------------+------------------------+-----------------------+
|Exclusions                   |                        |Indicates the list of  |
|                             |                        |files and folders not  |
|                             |                        |to back up.            |
+-----------------------------+------------------------+-----------------------+





**Example List All Backup Configurations For An Agent: JSON response**


.. code::

        [
            {
               "BackupConfigurationId": 158485,
               "MachineAgentId": 224193,
               "MachineName": "Web Server",
               "Flavor": "RaxCloudServer",
               "IsEncrypted": false,
               "BackupConfigurationName": "Manual Log Backup",
               "IsActive": true,
               "IsDeleted": false,
               "VersionRetention": 60,
               "BackupConfigurationScheduleId": 155566,
               "MissedBackupActionId": 1,
               "Frequency": "Manually",
               "StartTimeHour": null,
               "StartTimeMinute": null,
               "StartTimeAmPm": "",
               "DayOfWeekId": null,
               "HourInterval": null,
               "TimeZoneId": "Eastern Standard Time",
               "NextScheduledRunTime": "\/Date(-62135578800000)\/",
               "LastRunTime": null,
               "LastRunBackupReportId": null,
               "NotifyRecipients": "user@rackspace.com",
               "NotifySuccess": true,
               "NotifyFailure": true,
               "Inclusions": [
                   {
                       "FilePath": "C:\\Websites\\Logs",
                       "ParentId": 158485,
                       "FileItemType": "Folder",
                       "FileId": 47085
                   }
            ],
               "Exclusions": [ ]
         },
         {
               "BackupConfigurationId": 158486,
               "MachineAgentId": 224193,
               "MachineName": "Web Server",
               "Flavor": "RaxCloudServer",
               "IsEncrypted": false,
               "BackupConfigurationName": "Weekly Website Backup",
               "IsActive": true,
               "IsDeleted": false,
               "VersionRetention": 60,
               "BackupConfigurationScheduleId": 155567,
               "MissedBackupActionId": 1,
               "Frequency": "Weekly",
               "StartTimeHour": 7,
               "StartTimeMinute": 23,
               "StartTimeAmPm": "AM",
               "DayOfWeekId": 1,
               "HourInterval": null,
               "TimeZoneId": "Eastern Standard Time",
               "NextScheduledRunTime": "\/Date(1358752980000)\/",
               "LastRunTime": null,
               "LastRunBackupReportId": null,
               "NotifyRecipients": "user@rackspace.com",
               "NotifySuccess": true,
               "NotifyFailure": true,
               "Inclusions": [
                    {
                       "FilePath": "C:\\Websites",
                       "ParentId": 158486,
                       "FileItemType": "Folder",
                       "FileId": 47086
                    },
                    {
                       "FilePath": "C:\\Websites\\Logs",
                       "ParentId": 158486,
                       "FileItemType": "Folder",
                       "FileId": 47087
                    }
                ],
                "Exclusions": [ ]
            }
         ]


