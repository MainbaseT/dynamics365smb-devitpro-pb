---
title: "Notification Data Type"
description: "Provides a programmatic way to send non-intrusive information to the user interface (UI) in the Business Central Web client."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# Notification Data Type
> **Version**: _Available or changed with runtime version 1.0._

Provides a programmatic way to send non-intrusive information to the user interface (UI) in the Business Central Web client.



## Instance methods
The following methods are available on instances of the Notification data type.

|Method name|Description|
|-----------|-----------|
|[AddAction(Text, Integer, Text)](notification-addaction-string-integer-string-method.md)|Specifies an action for the notification.|
|[AddAction(Text, Integer, Text, Text)](notification-addaction-string-integer-string-string-method.md)|Specifies an action for the notification.|
|[GetData(Text)](notification-getdata-method.md)|Retrieves data that was passed to a notification instance as specified by a SETDATA method call.|
|[HasData(Text)](notification-hasdata-method.md)|Checks if data was passed to a notification instance as specified by a SETDATA method call.|
|[Id([Guid])](notification-id-method.md)|Specifies the identifier for a notification.|
|[Message([Text])](notification-message-method.md)|Specifies the content of the notification.|
|[Recall()](notification-recall-method.md)|Recall a sent notification.|
|[Scope([NotificationScope])](notification-scope-method.md)|Specifies the context in which the notification appears in the client.|
|[Send()](notification-send-method.md)|Sends the notification to the client, where it will display in the UI.|
|[SetData(Text, Text)](notification-setdata-method.md)|Specifies a data property value for the notification. The data is specified as text in a key-value pair.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Notifications](../../devenv-notifications-developing.md)  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  