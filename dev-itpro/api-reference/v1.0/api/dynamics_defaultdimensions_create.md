---
title: (v1.0) Create defaultDimensions for entities
description: (v1.0) Creates a default dimensions of the item object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen
ms.custom: evergreen
ms.topic: reference
ms.devlang: al
ms.date: 05/01/2024
ms.update-cycle: 1095-days
ms.author: solsen
ms.reviewer: solsen
---

# Create defaultDimensions for entities (v1.0)
Creates the default dimensions for entities in [!INCLUDE[prod_short](../../../includes/prod_short.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[prod_short](../../../includes/prod_short.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).
```
POST businesscentralPrefix/companies({companyId})/items({itemId})/defaultDimensions
```

## Request headers (v1.0)

|Header         |Value                    |
|---------------|-------------------------|
|Authorization  |Bearer {token}. Required.|
|Content-Type   |application/json         |

## Request body (v1.0)
In the request body, supply a JSON representation of **defaultDimensions** object.

## Response (v1.0)
If successful, this method returns ```201 Created``` response code and a **defaultDimensions** object in the response body.

## Example (v1.0)

**Request**  
Here is an example of a request.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
POST https://{businesscentralPrefix}/api/v1.0/companies({companyId})/items({itemId})/defaultDimensions
POST https://{businesscentralPrefix}/api/v1.0/companies({companyId})/vendors({vendorId})/defaultDimensions
POST https://{businesscentralPrefix}/api/v1.0/companies({companyId})/employees({employeeId})/defaultDimensions
POST https://{businesscentralPrefix}/api/v1.0/companies({companyId})/customers({customerId})/defaultDimensions

```

**Request body**

```json
{
    "parentId":"b3fbe87a-61b8-4a6c-85de-0555f1627a67",
    "dimensionId":"d5fc81ea-8687-4e9d-9c49-7fde28ccdb1a",
    "dimensionValueId":"1045a902-070a-4d31-b2b1-b9431e9e5b26",
    "postingValidation":"Same Code"
}
```
**Response**

```json
{
    "@odata.context":"https://api.businesscentral.dynamics.com/v1.0/api/v1.0/$metadata#companies(5106c77d-af37-4e2d-bb88-45d87aba1033)/items(b3fbe87a-61b8-4a6c-85de-0555f1627a67)/defaultDimensions",
    "value":
    [
        {
            "@odata.etag":"W/\"JzQ0OzNPaHFuS0ZQdk5oc3ZkSW9KdzVkdXk2LytjcmNqeHJJOU05SjZ1aFBYVjQ9MTswMDsn\"",
            "parentId":"b3fbe87a-61b8-4a6c-85de-0555f1627a67",
            "dimensionId":"d5fc81ea-8687-4e9d-9c49-7fde28ccdb1a",
            "dimensionCode":"DEPARTMENT",
            "dimensionValueId":"1045a902-070a-4d31-b2b1-b9431e9e5b26",
            "dimensionValueCode":"PROD",
            "postingValidation":"Same Code"
        }
    ]
}
```

## Related information
[Tips for working with the APIs](../../../developer/devenv-connect-apps-tips.md)    

[defaultDimension resource](../resources/dynamics_defaultDimension.md)  
[Get defaultDimensions](../api/dynamics_defaultdimensions_get.md)  
[Update defaultDimensions](../api/dynamics_defaultdimensions_update.md)  
[Delete defaultDimensions](../api/dynamics_defaultdimensions_delete.md)  
