
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

List Events For A Backup
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{project_id}/backups/{backup_id}/events

Lists events for the specified backup.

This operation lists all events for the specified backup. You should consider these events to be transient because they might disappear after a minute or so. Therefore, this operation is most useful for monitoring a running backup. 



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |                         |
+--------------------------+-------------------------+-------------------------+
|400                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|401                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|403                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|404                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|405                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|409                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|500                       |                         |                         |
+--------------------------+-------------------------+-------------------------+
|503                       |                         |                         |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{project_id}              |xsd:string               |Project ID of the user.  |
|                          |                         |Also referred to as the  |
|                          |                         |tenant ID or account ID. |
+--------------------------+-------------------------+-------------------------+
|{backup_id}               |xsd:string *(Required)*  |Backup ID. For example,  |
|                          |                         |``0d95d699-d16b-11e4-    |
|                          |                         |93bd-c8e0eb190e3d``.     |
+--------------------------+-------------------------+-------------------------+



This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|marker                    |xsd:string *(Optional)*  |ID of the event, for     |
|                          |                         |example, ``5152883998``. |
|                          |                         |Only events newer than   |
|                          |                         |the event specified by   |
|                          |                         |marker are returned. Use |
|                          |                         |of ``marker`` is most    |
|                          |                         |useful when you are      |
|                          |                         |continuously monitoring  |
|                          |                         |this endpoint for new    |
|                          |                         |events, so that old      |
|                          |                         |events are not repeated  |
|                          |                         |back to you in           |
|                          |                         |subsequent calls.        |
+--------------------------+-------------------------+-------------------------+
|limit                     |xsd:integer *(Optional)* |Number of events to      |
|                          |                         |list. The default value  |
|                          |                         |is 100.                  |
+--------------------------+-------------------------+-------------------------+
|sort_dir                  |xsd:string *(Optional)*  |Direction to sort the    |
|                          |                         |results. Valid values    |
|                          |                         |are ``asc`` and          |
|                          |                         |``desc``. The default    |
|                          |                         |value is ``desc``.       |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example List Events For A Backup: JSON request**


.. code::

    GET https://dfw.backup.api.rackspacecloud.com/v2/110011/backups/0d95d699-d16b-11e4-93bd-c8e0eb190e3d/events?marker=5152883998&limit=100&sort_dir=desc HTTP/1.1
    Host: dfw.backup.api.rackspacecloud.com
    X-Auth-Token: 0f6e9f63600142f0a970911583522217
    Content-type: application/json


Response
""""""""""""""""


This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|events                    |                         |Information about events |
|                          |                         |for the backup.          |
+--------------------------+-------------------------+-------------------------+
|id                        |                         |ID of the event.         |
+--------------------------+-------------------------+-------------------------+
|time                      |                         |Time of the event.       |
+--------------------------+-------------------------+-------------------------+
|event                     |                         |Type of the event.       |
+--------------------------+-------------------------+-------------------------+
|agent                     |                         |Information about the    |
|                          |                         |agent for each ``event``.|
+--------------------------+-------------------------+-------------------------+
|id                        |                         |ID of the agent.         |
+--------------------------+-------------------------+-------------------------+
|vault                     |                         |Information about the    |
|                          |                         |vault for the backup.    |
+--------------------------+-------------------------+-------------------------+
|id                        |                         |ID of the vault.         |
+--------------------------+-------------------------+-------------------------+
|encrypted                 |                         |Specifies whether the    |
|                          |                         |vault is encrypted.      |
+--------------------------+-------------------------+-------------------------+
|configuration             |                         |Information about the    |
|                          |                         |configuration for each   |
|                          |                         |``event``.               |
+--------------------------+-------------------------+-------------------------+
|id                        |                         |ID of the configuration. |
+--------------------------+-------------------------+-------------------------+
|backup                    |                         |Information about the    |
|                          |                         |backup for each          |
|                          |                         |``event``.               |
+--------------------------+-------------------------+-------------------------+
|id                        |                         |ID of the backup.        |
+--------------------------+-------------------------+-------------------------+
|snapshot_id               |                         |ID of the snapshot.      |
+--------------------------+-------------------------+-------------------------+
|request_id                |                         |ID of the request.       |
+--------------------------+-------------------------+-------------------------+
|bytes_completed           |                         |Number of bytes          |
|                          |                         |completed.               |
+--------------------------+-------------------------+-------------------------+
|bytes_remaining           |                         |Number of bytes          |
|                          |                         |remaining.               |
+--------------------------+-------------------------+-------------------------+
|total_bytes               |                         |Total number of bytes.   |
+--------------------------+-------------------------+-------------------------+
|path                      |                         |Path for the browse      |
|                          |                         |request.                 |
+--------------------------+-------------------------+-------------------------+
|path_encoded              |                         |Encoded path for the     |
|                          |                         |browse request.          |
+--------------------------+-------------------------+-------------------------+
|encrypted_password_hex    |                         |Encrypted password in    |
|                          |                         |hexadecimal notation.    |
+--------------------------+-------------------------+-------------------------+
|links                     |                         |Links for the next and   |
|                          |                         |previous events.         |
+--------------------------+-------------------------+-------------------------+
|href                      |                         |Location (URI).          |
+--------------------------+-------------------------+-------------------------+
|rel                       |                         |How the href link        |
|                          |                         |provided is related to   |
|                          |                         |this resource URI.       |
+--------------------------+-------------------------+-------------------------+





**Example List Events For A Backup: JSON response**


.. code::

    200 (OK)
    Content-Type: application/json


