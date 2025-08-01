---
title: (v1.0) cashFlowStatement resource type
description: (v1.0) A cash flow statement object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen
ms.custom: evergreen
ms.topic: reference
ms.devlang: al
ms.date: 05/01/2024
ms.update-cycle: 1095-days
ms.author: solsen
ms.reviewer: solsen
---

# cashFlowStatement resource type (v1.0)

[!INCLUDE[d365_api_newversion](../../../includes/d365_api_newversion.md)]

Represents an cashFlowStatement object in [!INCLUDE[prod_short](../../../includes/prod_short.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[prod_short](../../../includes/prod_short.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:-------------|:-------------|:----------|
|[GET cashFlowStatement](../api/dynamics_cashflowstatement_get.md)|cashFlowStatement|Get a cashFlowStatement object.|

## Properties

| Property     | Type   |Description                              |
|:-------------|:-------|:----------------------------------------|
|lineNumber    |numeric |The cashFlowStatement item line number.  |
|display       |string  |The cashFlowStatement item display name. |
|netChange     |numeric |The cashFlowStatement item Net Change.   |
|lineType      |string  |The cashFlowStatement item line type can be: header, detail, total, or spacer.|
|indentation   |numeric |The cashFlowStatement item indentation used in report layout.|
|dateFilter    |date    |The date filter used to calculate the cashFlowStatement items.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "lineNumber": "int",
    "display": "string",
    "netChange": "decimal",
    "lineType": "string",
    "indentation": "int",
    "dateFilter": "date"
}
```
## Related information
  
[Get Cash Flow Statement](../api/dynamics_cashflowstatement_get.md)  
[Balance Sheet](dynamics_balancesheet.md)  
