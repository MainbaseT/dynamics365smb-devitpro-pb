---
title: "TestPart.Prev() Method"
description: "Sets the current row of the test page as the previous row in the data set."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# TestPart.Prev() Method
> **Version**: _Available or changed with runtime version 3.0-13.0-true until version 3.0 where it was deprecated for the following reason: "Use Previous instead."_

Sets the current row of the test page as the previous row in the data set.


## Syntax
```AL
[Ok := ]  TestPart.Prev()
```
## Parameters
*TestPart*  
&emsp;Type: [TestPart](testpart-data-type.md)  
An instance of the [TestPart](testpart-data-type.md) data type.  

## Return Value
*[Optional] Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
True, if the current row has changed.


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[TestPart Data Type](testpart-data-type.md)  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)