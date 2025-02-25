---
title: "JsonValue.AsTime() Method"
description: "Converts the value in a JsonValue to a Time data type."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# JsonValue.AsTime() Method
> **Version**: _Available or changed with runtime version 1.0._

Converts the value in a JsonValue to a Time data type.


## Syntax
```AL
Result :=   JsonValue.AsTime()
```
## Parameters
*JsonValue*  
&emsp;Type: [JsonValue](jsonvalue-data-type.md)  
An instance of the [JsonValue](jsonvalue-data-type.md) data type.  

## Return Value
*Result*  
&emsp;Type: [Time](../time/time-data-type.md)  
If the JsonValue does not contain a string of the format "HH:mm:ss.FFFFFFF" ( see Custom Date and Time Format Strings) the operation will fail with a run-time error.


[//]: # (IMPORTANT: END>DO_NOT_EDIT)


## See Also
[JsonValue Data Type](jsonvalue-data-type.md)  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)