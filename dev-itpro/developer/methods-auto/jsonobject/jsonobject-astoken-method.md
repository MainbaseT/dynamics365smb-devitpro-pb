---
title: "JsonObject.AsToken() Method"
description: "Converts the value in a JsonObject to a JsonToken data type."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# JsonObject.AsToken() Method
> **Version**: _Available or changed with runtime version 1.0._

Converts the value in a JsonObject to a JsonToken data type.


## Syntax
```AL
Token :=   JsonObject.AsToken()
```
## Parameters
*JsonObject*  
&emsp;Type: [JsonObject](jsonobject-data-type.md)  
An instance of the [JsonObject](jsonobject-data-type.md) data type.  

## Return Value
*Token*  
&emsp;Type: [JsonToken](../jsontoken/jsontoken-data-type.md)  
The returned JsonToken contains the same data as the JsonObject, but allows for treating the data in a generic manner.


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[JsonObject Data Type](jsonobject-data-type.md)  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)