---
title: "OnCheckPreconditionsPerCompany (Codeunit) Trigger"
description: "Runs before an extension upgrade."
ms.author: solsen
ms.date: 03/11/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)

# OnCheckPreconditionsPerCompany (Codeunit) Trigger
> **Version**: _Available or changed with runtime version 1.0._

Runs before an extension upgrade.

> [!IMPORTANT]
> The [Subtype Property](../../properties/devenv-subtype-property.md) must be set to **Upgrade** in the Codeunit.

## Syntax
```AL
trigger OnCheckPreconditionsPerCompany()
begin
    ...
end;
```



[//]: # (IMPORTANT: END>DO_NOT_EDIT)

> [!NOTE]  
>  This trigger is also available in upgrade codeunits for the base application, not just for extensions.  

## Remarks  
It is used to check that certain requirements are met in order to run the upgrade.If an error occurs during runtime the extension upgrade is canceled.

This trigger is run once for each company in the database, and it is executed within its own system session for the company.

## See Also  
[Get Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  
