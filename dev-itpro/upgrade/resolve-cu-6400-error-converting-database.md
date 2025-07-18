---
title: "Resolving Codeunit 6400 Compilation Error "
description: "Explains how to resolve the compilation error that you get for Codeunit 6400 when converting a database from Dynamics NAV to Business Central."
ms.custom: evergreen
ms.date: 04/18/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
author: jswymer
---
# Resolving Codeunit 6400 Compilation Error 
This article explains how to resolve the compilation error that you get for codeunit **6400 Flow Template Selector** when converting a [!INCLUDE[nav2018_md](../developer/includes/nav2018_md.md)] database to  [!INCLUDE[prodhort](../developer/includes/prod_short.md)].

## Resolution

Add the following functions:

```
[External]
PROCEDURE GetAzureADGraphhResourceUrl@4() : Text;
BEGIN
  EXIT(AzureADGraphResourceUrlTxt);
END;

[External]
PROCEDURE GetMicrosoftGraphhResourceUrl@31() : Text;
BEGIN
  EXIT(MicrosoftGraphResourceUrlTxt);
END;
```

Add the following global text variable:
```
AzureADGraphResourceUrlTxt@1018 : TextConst '@@@={Locked};ENU=https://graph.windows.net';
MicrosoftGraphResourceUrlTxt@1009 : TextConst '@@@={Locked};ENU=https://graph.microsoft.com';
```


## Related information  
 [Converting a Database](Converting-a-Database.md)  
 [Resolving Compilation Errors When Converting a Dynamics NAV 2018 Database](Resolve-Compile-Errors-When-Converting-Dynamics-NAV-2018-Database.md)  
