---
title: Security Auditing in Business Central
description: Learn about the built-in capabilities in Business Central that let you track and audit usage of your Business Central.
author: jswymer

ms.topic: conceptual
ms.author: jswymer
ms.date: 04/01/2021
---

# Security Auditing in Business Central

[!INCLUDE[prod_short](../developer/includes/prod_short.md)] includes a change log that lets you track all direct modifications that a user makes to data in the database. In addition, the change log always records changes to various system tables, which enables you to track changes to security sub-systems like users and permissions.

Some of the most important tables tracked include:  

- Table 2000000053 Access Control

- Table 2000000005 Permission

- Table 2000000004 Permission Set

- Table 2000000120 User

- Table 2000000121 User Property

- Table 402 Change Log Setup

- Table 403 Change Log Setup

- Table 404 Change Log Setup (Field)

> [!IMPORTANT]  
> The change log on the above tables is always turned on and cannot be turned off by using **Change Log Setup** page in the client.
>
> The change log code is called from the `OnDatabaseInsert` method in the system codeunit **49 GlobalTriggerManagemnet**.

For more information, see [Auditing Changes in Business Central](/dynamics365/business-central/across-log-changes).

<!-- change title to auditing data changes -->
## See Also  

[Security Development Lifecycle](https://www.microsoft.com/sdl)  
