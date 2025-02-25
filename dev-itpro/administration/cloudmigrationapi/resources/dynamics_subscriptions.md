---
title: subscriptions resource type
description: A subscriptions object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.topic: reference
ms.devlang: al
ms.date: 03/25/2022
ms.author: solsen
---

# subscriptions resource type

<!-- START>DO_NOT_EDIT -->
<!-- IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT. -->
Represents a subscriptions in [!INCLUDE[prod_short](../../../includes/prod_short.md)].

> [!NOTE]
> For information about enabling APIs for [!INCLUDE[prod_short](../../../includes/prod_short.md)] see [guideline](../../../api-reference/v2.0/endpoints-apis-for-dynamics.md).

## Methods

| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET subscriptions](../api/dynamics_subscriptions_get.md)|subscriptions|Gets a subscriptions object.|
|[DELETE subscriptions](../api/dynamics_subscriptions_delete.md)|none|Deletes a subscriptions object.|
|[POST subscriptions](../api/dynamics_subscriptions_create.md)|subscriptions|Creates a subscriptions object.|
|[PATCH subscriptions](../api/dynamics_subscriptions_update.md)|subscriptions|Updates a subscriptions object.|



## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|subscriptionId|string|Unique key for the subscription.|
|notificationUrl|string|URL to which webhook notifications are sent.|
|resource|string|URL for the resource being subscribed to. Supports relative and absolute URL.|
|userId|GUID|The ID of user that has created the subscriptions.|
|lastModifiedDateTime|datetime|The last datetime the subscriptions was modified. Read-Only.|
|clientState|string|Client state will be delivered with every notification. This can be used as a secret to verify message or for managing state if needed.|
|expirationDateTime|datetime|Date and time for when the webhook will expire.|
|systemCreatedAt|datetime|The datetime the company was created.|
|systemCreatedBy|GUID|The ID of the user who created the company.|
|systemModifiedAt|datetime|The last datetime the subscriptions was modified.|
|systemModifiedBy|GUID|The ID of the user who last modified the company.|
|estimatedSize|decimal|Read-Only property representing the approximate size of the On-Prem company. The data migrated will be smaller, since the data will be compressed and not all tables will be included.|
|created|boolean|Specifies if the company was created. It will not reflect if the setup of the company was correct or not. For this you should check the status property. If the company has been created, however status is different.|


## JSON representation

Here is a JSON representation of the subscriptions resource.


```json
{
    "subscriptionId": "string",
    "notificationUrl": "string",
    "resource": "string",
    "userId": "GUID",
    "lastModifiedDateTime": "datetime",
    "clientState": "string",
    "expirationDateTime": "datetime",
    "systemCreatedAt": "datetime",
    "systemCreatedBy": "GUID",
    "systemModifiedAt": "datetime",
    "systemModifiedBy": "GUID"
}
```
<!-- IMPORTANT: END>DO_NOT_EDIT -->

## See Also
[GET subscriptions](../api/dynamics_subscriptions_get.md)  
[DELETE subscriptions](../api/dynamics_subscriptions_delete.md)  
[POST subscriptions](../api/dynamics_subscriptions_create.md)  
[PATCH subscriptions](../api/dynamics_subscriptions_update.md)
