---
title: "XmlNode.AsXmlDeclaration() Method"
description: "Converts the node to an XmlDeclaration node."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# XmlNode.AsXmlDeclaration() Method
> **Version**: _Available or changed with runtime version 1.0._

Converts the node to an XmlDeclaration node. The operation will fail if the node is not an XmlDeclaration.


## Syntax
```AL
XmlDeclaration :=   XmlNode.AsXmlDeclaration()
```
## Parameters
*XmlNode*  
&emsp;Type: [XmlNode](xmlnode-data-type.md)  
An instance of the [XmlNode](xmlnode-data-type.md) data type.  

## Return Value
*XmlDeclaration*  
&emsp;Type: [XmlDeclaration](../xmldeclaration/xmldeclaration-data-type.md)  
An XmlDeclaration value that references the current XmlNode.


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[XmlNode Data Type](xmlnode-data-type.md)  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)