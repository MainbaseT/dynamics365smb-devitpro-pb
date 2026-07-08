---
title: Moving between extension scopes
description: Describes how an extension in one scope can be moved into another scope in Business Central.
ms.author: solsen
ms.date: 05/02/2025
ms.topic: concept-article
author: SusanneWindfeldPedersen
ms.reviewer: solsen
---

# Moving between extension scopes

This article describes the different options you have for moving an app from one scope to another.

For a definition of the different extension types and their scope, see [Extension types and scope](devenv-extension-types-and-scope.md).

## Moving a PTE to Marketplace

**Scenario:** You deployed your extension for selected customers as a PTE and now want to cover more markets by deploying it as a Marketplace app.

### Identity requirements for moving a PTE to Marketplace

- It isn't possible to deploy a Marketplace app and a PTE with the same `id`. You must then change the `id` of the extension before uploading it to Marketplace. This means that the data won't be available anymore for environments that had the PTE installed and are now using the Marketplace app. Dependent extensions also must be updated to use the new app ID in their `app.json` file.

- Due to some current limitations in our service, it isn't possible to have a Marketplace app and a PTE extension with the same `name`, `publisher`, and `version`. You must then change the `name`, `publisher`, or `version` of the app before uploading it to Marketplace.

### Other requirements for moving a PTE to Marketplace

- Marketplace apps and PTEs are using different ID ranges. You must then change the ID of all the objects in your extension. Learn more in [Object ranges](devenv-object-ranges.md).

- Marketplace apps are required to use affixes for their object names, while PTEs don't have any affix usage requirements. You might then have to rename all the objects in your extension to use affixes. Learn more in [Benefits and guidelines for using a prefix or suffix](../compliance/apptest-prefix-suffix.md).

- You can find the full list of requirements for Marketplace apps here:  
  - [Technical Validation Checklist](devenv-checklist-submission.md)
  - [Marketing Validation Checklist](readiness/readiness-checklist-marketing.md)

### Other information for moving a PTE to Marketplace

- If you want to move the data by having the two apps (PTE and Marketplace app) installed side-by-side, then you must ensure that the two apps can be installed side-by-side. For this, they must not share any object names nor IDs. You can then define another PTE depending on both apps that would take care of moving the data.

- Update all dependent extensions to use the new app ID in their `app.json` file and to reference the objects defined in the extension by their new name and object ID.


## Moving a DEV extension to Marketplace

**Scenario:** You're done developing a new offer or a new version of an existing offer and are now ready to make it available for all your customers in SaaS.

### Identity requirements for moving a DEV extension to Marketplace

- It's not possible to deploy a Marketplace app and a PTE with the same `id`. You must then change the `id` of the extension before uploading it to Marketplace. This means that the data won't be available anymore for environments that had the PTE installed and are now using the Marketplace app. Dependent extensions need to be updated to use the new app ID in their `app.json` file.

- Due to some current limitations in our service, it isn't possible to have a Marketplace app and a PTE extension with the same `name`, `publisher`, and `version`. You must then change the `name`, `publisher`, or `version` of the app before uploading it to Marketplace.

> [!NOTE]  
> Alternatively, you can also uninstall and unpublish the DEV extension with this app `id` from your sandbox environment. Make sure to select the option to delete the extension data and extension schema when uninstalling the extension.

### Other requirements for moving a DEV extension to Marketplace

- Marketplace apps must use a specific ID range, while DEV extensions don't have any ID range limitation. You might need to change the ID of all the objects in your extension. For more information, see [Object ranges](devenv-object-ranges.md).

- Marketplace apps must use affixes for their object names, while DEV extensions don't have any affix usage requirements. You might need to rename all the objects in your extension to use affixes. For more information, see [Benefits and guidelines for using a prefix or suffix](../compliance/apptest-prefix-suffix.md).

- You can find the full list of requirements for Marketplace apps here:  
  - [Technical Validation Checklist](devenv-checklist-submission.md)
  - [Marketing Validation Checklist](readiness/readiness-checklist-marketing.md)


## Publishing a Marketplace app as a DEV extension

**Scenario:** Showing a preview of an app to a customer or developing the next version of the app.

Publishing a Marketplace app to a sandbox environment as a DEV extension is a common scenario when you want to show a preview of your app to a customer or during active development.

> [!NOTE]  
> From [!INCLUDE[prod_short](../includes/prod_short.md)] 2023 release wave 2, it's possible to install a preview of Marketplace apps on customer environments without publishing them as DEV extensions. Learn more in [Technical Validation FAQ](devenv-checklist-submission-app-preview.md).

### Identity requirements for publishing a Marketplace app as a DEV extension

- DEV extensions should have a different app `id` because there might be other global apps published to your service and they collide. If you don't change the app `id`, the app that you published from Visual Studio Code to a developer sandbox is automatically unpublished from your environment if another user tries to install the Marketplace app in their environment.

### Other requirements for publishing a Marketplace app as a DEV extension

- If you don't change the app `id` of the Marketplace app in your DEV extension, publishing the DEV extension is prevented when another Marketplace app depends on that particular Marketplace app. To achieve such functionality, publish the whole chain of dependencies as DEV extensions with different app `id` values.

## Publishing a PTE as a DEV extension

**Scenario:** Showing a preview of an app to a customer or developing the next version of the app.

### Identity requirements for publishing a PTE as a DEV extension

No specific identity requirements.

### Other requirements for publishing a PTE as a DEV extension

No specific requirements.

## Moving a DEV extension to a PTE

**Scenario:** Deploying your app to a production environment.

### Identity requirements for moving a DEV extension to a PTE

No specific identity requirements.

### Other requirements for moving a DEV extension to a PTE

You can find the full list of requirements for PTE in the documentation for the [PerTenantExtensionCop Analyzer](analyzers/pertenantextensioncop.md).

## Moving a Marketplace app to a PTE

**Scenario:** Reducing the availability of your app to select customers.

### Identity requirements for moving a Marketplace app to a PTE

- You can't deploy a Marketplace app and a PTE with the same `id`. You must change the `id` of the extension before deploying it as a PTE. This change means that the data isn't available anymore for environments that had the Marketplace app installed and are now using the PTE. You need to update dependent extensions to use the new app ID in their `app.json` file.

- If you wish to deprecate the offer in Marketplace, see [Discontinuing a Marketplace app](devenv-app-discontinue.md).

### Other requirements for moving a Marketplace app to a PTE

- Marketplace apps and PTEs use different ID ranges. You must change the ID of all the objects in your extension. To learn more, see [Object ranges](devenv-object-ranges.md).

- To avoid potential name conflicts if the Marketplace app and the PTE are installed side-by-side, change the name of all the objects in your extension.

- You can find the full list of requirements for PTE in the documentation for the [PerTenantExtensionCop Analyzer](analyzers/pertenantextensioncop.md).

### Other information for moving a Marketplace app to a PTE

- Even if you stop distributing the offer in Partner Center, the app still exists in [!INCLUDE[prod_short](../includes/prod_short.md)] and the app ID remains reserved for it. You can't attribute the app ID to the PTE.

- If you want to move the data by having the two apps (PTE and Marketplace app) installed side-by-side, then you must ensure that the two apps can be installed side-by-side. For this, they must not share any object names nor IDs. You can then define another PTE depending on both apps that would take care of moving the data.

- All dependent extensions have to be updated to use the new app `id` in their `app.json` file and to reference the objects defined in the extension by their new name and object ID.


## Related information

[Developing extensions](devenv-dev-overview.md)  
[Get started with AL](devenv-get-started.md)  
[Extension types and scope](devenv-extension-types-and-scope.md)
