---
author: jswymer
ms.topic: include
ms.date: 11/01/2024
ms.author: jswymer
ms.reviewer: jswymer
ms.custom: sfi-ga-nochange
---

Delegated administrators aren't visible in the customer's Microsoft Entra ID user list and can't be managed by the customer's internal admin. However, when a delegated administrator logs into a [!INCLUDE [prod_short](prod_short.md)] environment, they're automatically created as a user in the environment. This way, the actions performed by a delegated administrator, such as posting documents, are logged and associated with their user ID.

When a delegated administrator first signs in to an environment, the user is created and default permissions are assigned based on the license configuration. Users created for delegated administrators aren't shown with name and other personal information but with a unique ID and their company name. Both internal and external admins can see these users in the **Users** list, and they have full transparency into what these users do through the [change log](/dynamics365/business-central/across-log-changes), for example. GDAP users are listed with user names such as `USER_1A2B3C4D5E6F`, and an email address such as `USER_1A2B3C4D5E6F@contoso.com`, which isn't the person's actual email address. Because they aren't part of their customer's Microsoft Entra ID, their authentication email address isn't an email address at all but reflects the company that they work for, such as `Contoso`. This way, the GDAP user accounts don't reveal personal information. If you need to find out who the person behind such a pseudonym is, you'll have to reach out to the company that this user works or worked for.  

License configurations determine the default permissions a delegated user gets upon first sign in to an environment. Delegated Dynamics 365 Business Central Administrators are assigned the permissions defined in the **Delegated BC Admin agent - Partner** license configuration. Delegated Global Administrators are assigned the permissions defined in the **Delegated Admin agent - Partner** license configuration. Delegated Helpdesk Administrators are assigned the permissions in the **Delegated Helpdesk agent - Partner** license configuration. After the delegated administrator user is created in the environment, their permissions can be changed from the permissions that were assigned by default. Learn more at [Configure permissions based on licenses](/dynamics365/business-central/ui-how-users-permissions#licensespermissions) and [Assign permissions to users and groups](/dynamics365/business-central/ui-define-granular-permissions).
