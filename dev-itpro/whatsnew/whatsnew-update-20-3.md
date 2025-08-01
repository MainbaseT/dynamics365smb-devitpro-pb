---
title: "Update 20.3 for Microsoft Dynamics 365 Business Central 2022 Release Wave 1"
description: Get an overview of new and changed capabilities in the 20.3 update of Business Central online, which is part of 2022 release wave 1.
ms.author: jswymer
ms.date: 04/01/2024
ms.update-cycle: 1095-days
ms.reviewer: jswymer
ms.topic: article
author: jswymer
ms.custom: evergreen
---

# Update 20.3 for Microsoft Dynamics 365 Business Central online 2022 release wave 1

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Would you like to know what has changed in update 20.3? Below you'll find an overview and relevant links to what has been done on hotfixes and regulatory features in this update. In addition, we've gathered some good to know information and links, you might find interesting.

## Hotfixes

Find an overview of hotfixes in this [article](https://support.microsoft.com/help/5016304).

## Feature changes

- [Improved settings for managing updates](/dynamics365-release-plan/2022wave1/smb/dynamics365-business-central/improved-settings-managing-updates) (read more [here](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-update-management))
- [New AppSourceCop allowing you to run validation to determine any code hit by obsoleted objects for a given future version](/dynamics365/business-central/dev-itpro/developer/analyzers/appsourcecop-as0105)
- As continuation for [Support inventory pick and warehouse pick operations for jobs](/dynamics365-release-plan/2022wave1/smb/dynamics365-business-central/support-inventory-pick-warehouse-pick-operations-jobs), we introduce  a **To-Job Bin Code** field on the **Location Card** page to support warehouse pick scenarios. You can also use it in inventory picks if you prefer a specific bin to be set on a job planning line.

## Localization updates

| Country| Feature  |Description|
|-------------|--------------|--------------|
|W1 | Extended text functionality for VAT clauses | In some situations and countries/regions, VAT Clauses can take more than allowed number of characters. Because of that Extended Texts logic is implemented in the VAT Clauses and this extended text can be shown on the sales invoice. |
| Germany | Enhancements to Business Data Export file (GDPdU / GoDB) | Export file will use table and field names instead of captions. Also table and field names won't be limited to 20 characters and it will show full name, with blanks, dots, etc.|

## Release Plan  

If you want to get a comprehensive overview of what's new and planned for Business Central online for the entire 2022 release wave 1 (releases from April 2022 through September 2022), find the link to the release plan [here](/dynamics365-release-plan/2021wave2/smb/dynamics365-business-central/planned-features).

## Upgrade to 20.3

Please note that new customers will automatically get the latest builds of Business Central (20.3). If you're an existing partner/customer, you'll receive an email notification as soon as your environment has been upgraded.

## Good to know

**A single tile to go to Business Central**  
During July 2022, we're rolling out a change to online customers where a single Business Central tile in the App Launcher will be used to access both production and sandbox environments. Learn more [here](/dynamics365-release-plan/2022wave1/smb/dynamics365-business-central/single-tile-go-business-central).

**UI glitches introduced by recent browser updates**  
On Wednesday June 29, 2022, Microsoft began rolling out a fix for all Business Central online customers that addresses UI glitches introduced by a recent Chromium browser update. The fix will also be included in cumulative updates for supported versions of Business Central on premises. Learn how on premises customers can fix or work around the issue [here](https://go.microsoft.com/fwlink/?linkid=2201014).

**General availability of the Shopify Connector**  
In October 2021, we announced a new partnership with Shopify to help our customers create a better shopping experience. The partnership was designed to better connect the easy-to-use commerce and merchant experience of Shopify with the comprehensive business management capabilities of Microsoft Dynamics 365 Business Central. The Shopify connector is now available for Business Central online at no extra cost. Existing customers that have been upgraded to 20.1 or later automatically get the Shopify extension installed. If they don't need the app, it can be uninstalled by following [this guidance](/dynamics365/business-central/ui-extensions-install-uninstall#uninstall-an-extension). Read the [blog](https://cloudblogs.microsoft.com/dynamics365/bdm/2022/05/26/dynamics-365-business-central-now-includes-a-shopify-connector/), the [FAQ](/dynamics365/business-central/shopify/shopify-faq), watch the [on-demand session](https://aka.ms/BCShopifySession), learn how to [get started](/dynamics365/business-central/shopify/get-started) and view the listing on [Shopify App Store](https://apps.shopify.com/dynamics-365-business-central?surface_detail=global-erp-partners&surface_inter_position=1&surface_intra_position=1&surface_type=collection).

**Action required by July 2022 for Excel Add-in**  
Starting in July 2022, Microsoft will roll out an update to the Excel add-in that further secures the connection to Business Central. The update requires that you modify your organization's Microsoft Entra ID configuration so that users can continue using the add-in. This issue impacts all Business Central on-premises deployments that use the Excel add-in. Learn more [here](/dynamics365/business-central/dev-itpro/administration/update-excel-addin-configuration).

**Business Central newsletter for partners**  
Starting June 2022, we're doing quarterly newsletters for Business Central partners. Each newsletter will be a summary of relevant information related to Business Central and you'll be able to find it on [aka.ms/BCNews](https://aka.ms/BCNews).

**Discover resources on aka.ms/BCAll**  
Are you looking for relevant resources? Find it all in this article and remember to bookmark [aka.ms/BCAll](https://aka.ms/BCAll).

**Upcoming Business Central Office Hours Calls**  
The Business Central office hours calls will be unavailable in July. For August and September, we'll be hosting the following calls, which you can register for today:

- **August 23:** Excel Layout and reporting  
- **August 30:** You know, so share it in the docs for Dynamics 365 Business Central  
- **September 6:** Power Automate and Power Platform integrations  

Register and stay tuned for upcoming calls: [aka.ms/BCOfficeHours](https://aka.ms/BCOfficeHours). Watch on-demand recordings: [aka.ms/BCOfficeHoursRecordings](https://aka.ms/BCOfficeHoursRecordings).  

<!--**Business Central Launch Event**  
If you haven't watched them yet, remember that you still have access to a keynote and 20+ sessions about what's new in Business Central 2022 release wave 1. You'll hear from product leaders as they share with you the latest innovations and capabilities to help you confidently move to the cloud and unlock the insights needed to adapt faster, work smarter, and perform better. Whether you are a business professional, developer, or consultant at a Business Central partner, get ready to up level your game and drive business transformation. Register on [aka.ms/BCLE](https://aka.ms/BCLE)-->

