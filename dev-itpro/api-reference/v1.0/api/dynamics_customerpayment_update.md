---
title: (v1.0) Update customerPayments
description: (v1.0) Updates a customer payment object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen
ms.custom: evergreen
ms.topic: reference
ms.devlang: al
ms.date: 05/01/2024
ms.update-cycle: 1095-days
ms.author: solsen
ms.reviewer: solsen
---

# Update customerPayments (v1.0)
Update the properties of a customer payment object for [!INCLUDE[prod_short](../../../includes/prod_short.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[prod_short](../../../includes/prod_short.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).

```
PATCH businesscentralPrefix/companies({id})/customerPaymentsJournals({id})/customerPayments({id})
```

## Request headers (v1.0)

|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **customerPayments**, the **customerPayments** will not be updated.    |

## Request body (v1.0)
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response (v1.0)
If successful, this method returns a ```200 OK``` response code and an updated **customerPayments** object in the response body.

## Example (v1.0)

**Request**

Here is an example of the request.
```json
PATCH https://{businesscentralPrefix}/api/v1.0/companies({id})/customerPaymentsJournals({id})/customerPayments({id})
Content-type: application/json

{
  "amount": 2000
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "lineNumber": 10000,
  "customerId": "customerId-value",
  "customerNumber": "",
  "contactId": "contactId-value",
  "postingDate": "2015-12-31",
  "documentNumber": "D00001",
  "externalDocumentNumber": "",
  "amount": -2000,
  "appliesToInvoiceId": "appliesToInvoiceId-value",
  "appliesToInvoiceNumber": "100000",
  "description": "",
  "comment": "",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```
## Related information
[Tips for working with the APIs](../../../developer/devenv-connect-apps-tips.md)  



[Error Codes](../dynamics_error_codes.md)  
[Customer Payments](../resources/dynamics_customerpayment.md)  
[Get Customer Payments](dynamics_customerpayment_get.md)  
[Post Customer Payments](dynamics_create_customerpayment.md)  
[Delete Customer Payments](dynamics_customerpayment_delete.md)  