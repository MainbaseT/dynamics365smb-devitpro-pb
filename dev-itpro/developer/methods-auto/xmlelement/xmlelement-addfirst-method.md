---
title: "XmlElement.AddFirst(Any,...) Method"
description: "Adds the specified content at the start of the child list of this element."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# XmlElement.AddFirst(Any,...) Method
> **Version**: _Available or changed with runtime version 1.0._

Adds the specified content at the start of the child list of this element.


## Syntax
```AL
[Ok := ]  XmlElement.AddFirst(Content: Any,...)
```
## Parameters
*XmlElement*  
&emsp;Type: [XmlElement](xmlelement-data-type.md)  
An instance of the [XmlElement](xmlelement-data-type.md) data type.  

*Content*  
&emsp;Type: [Any](../any/any-data-type.md)  
The content to be added as a child of this element.  


## Return Value
*[Optional] Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.   If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[XmlElement Data Type](xmlelement-data-type.md)  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)