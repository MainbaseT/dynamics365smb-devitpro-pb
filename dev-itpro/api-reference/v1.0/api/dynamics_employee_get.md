---
title: (v1.0) Get employees
description: (v1.0) Gets an employee object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen
ms.custom: evergreen
ms.topic: reference
ms.devlang: al
ms.date: 05/01/2024
ms.update-cycle: 1095-days
ms.author: solsen
ms.reviewer: solsen
---

# Get employees (v1.0)
Retrieve the properties and relationships of an employee object for [!INCLUDE[prod_short](../../../includes/prod_short.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[prod_short](../../../includes/prod_short.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).
```
GET businesscentralPrefix/companies({id})/employees({id})
```

## Request headers (v1.0)

|Header       |Value                     |
|-------------|--------------------------|
|Authorization|Bearer {token}. Required. |

## Request body (v1.0)
Do not supply a request body for this method.

## Response (v1.0)
If successful, this method returns a ```200 OK``` response code and an **employees** object in the response body.

**Request**

Here is an example of the request.

```json
GET https://{businesscentralPrefix}/api/v1.0/companies({id})/employees({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "number": "AH",
  "displayName": "Annette Hill",
  "givenName": "Annette",
  "middleName": "",
  "surname": "Hill",
  "jobTitle": "Secretary",
  "address": {
    "street": "677 Fifth Avenue",
    "city": "New York",
    "state": "",
    "countryLetterCode": "",
    "postalCode": "10022"
  },
  "phoneNumber": "4465-4899-4643",
  "mobilePhone": "4564-4564-7831",
  "email": "",
  "personalEmail": "ah@cronus-demosite.com",
  "employmentDate": "2001-06-01",
  "terminationDate": "0001-01-01",
  "status": "Active",
  "birthDate": "1973-12-12",
  "picture@odata.mediaReadLink": "https://api.financials.dynamics.com/v1.0/api/v1.0/companies({id})/employees({id})/picture",
  "lastModifiedDateTime": "2017-03-16T14:57:19.497Z"  
}
```

## Related information
[Tips for working with the APIs](../../../developer/devenv-connect-apps-tips.md)  



[Error Codes](../dynamics_error_codes.md)  
[Employee](../resources/dynamics_employee.md)  
[Post Employee](../api/dynamics_create_employee.md)  
[Patch Employee](../api/dynamics_employee_update.md)  
[Delete Employee](../api/dynamics_employee_delete.md)  

