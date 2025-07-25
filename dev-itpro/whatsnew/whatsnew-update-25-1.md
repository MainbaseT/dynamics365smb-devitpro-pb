---
title: Update 25.1 for Microsoft Dynamics 365 Business Central 2024 release wave 2
description: Get an overview of new and changed capabilities in the 25.1 update of Business Central online, which is part of 2024 release wave 2.
ms.author: jswymer
ms.date: 10/29/2024
ms.update-cycle: 1095-days
ms.reviewer: jswymer
ms.topic: article
author: jswymer
ms.custom: 
    - bap-template
    - evergreen
---

# Update 25.1 for Microsoft Dynamics 365 Business Central online 2024 release wave 2

Would you like to know what changes are in update 25.1? Below you find an overview and relevant links to what was done on hotfixes and regulatory features in this update. In addition, we gathered some good to know information and links that you might find interesting.

## Hotfixes

Learn about the hotfixes on Microsoft Support at [Update 25.1 for Business Central 2024 release wave 2](https://support.microsoft.com/help/5047904). Download the on-premises files from the Microsoft Download Center at [Update 25.1 for Business Central](https://www.microsoft.com/en-us/download/details.aspx?id=106299)<!--(https://aka.ms/BCDownload)-->.

## Feature changes

- [Change the data search method in lists (general availability)](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/change-data-search-method-lists)
- [Report sustainability entries with financial reports (general availability)](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/reporting-sustainability-entries-financial-reports)
- [VAT Return feature now available - Czechia (general availability)](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/vat-return-czechia)
- [Use new service providers in the e-documents framework (public preview)](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/use-new-service-providers-e-documents-framework)

## Localization updates

No localization updates for 25.1.

## Release plan

Do you want to get a comprehensive overview of what's new and planned for Business Central online for the entire 2024 release wave 2 (release from October 2024 through March 2025)? Learn more at [Plan and prepare for Dynamics 365 Business Central in 2024 release wave 2](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/)<!--(https://aka.ms/BCReleasePlan)-->.

## Upgrade to 25.1

New customers automatically get the latest builds of Business Central (25.1). If you're an existing partner/customer, you receive an email notification as soon as your environment is upgraded.

## Good to know

### Enhancements to chat with Copilot coming in November

During November, we'll be releasing the [Experience enhancements to chat with Copilot](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/experience-enhancements-chat-copilot) feature.

### Business Central Launch Event videos on YouTube

The Business Central Launch Event for the 2024 release wave 2 took place on October 18, 2024. This online event aimed to provide information about the new features and enhancements in the 2024 release wave 2 to resellers, partners, ISVs, and consultants. You can find over 40 videos of this event on YouTube by visiting [aka.ms/BCLE](https://aka.ms/BCLE).

### Sales Order Agent in Business Central announcements

In October, the upcoming **Sales Order Agent** was announced in the Dynamics 365 blog post [Transform work with autonomous agents across your business processes](https://www.microsoft.com/en-us/dynamics-365/blog/business-leader/2024/10/21/transform-work-with-autonomous-agents-across-your-business-processes) and at the Microsoft Business Application Launch Event. This agent automates routine sales order tasks, allowing sales teams to focus more on customer engagement while improving order accuracy and speed.

To learn more, you can watch the [Business Application Launch Event video](https://vshow.on24.com/vshow/BALE?regPageId=21469#exhibits/Home1) (registration required) or read the highlights in the Dynamics 365 blog [2024 release wave 2 launches with hundreds of Copilot capabilities](https://aka.ms/BALE102924). Also, check out this short [video](https://www.youtube.com/watch?v=6icbmbLc_Og) on YouTube for a quick overview.

Follow the release plan at [Use Copilot with agent capabilities to automate sales order-taking](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/use-copilot-agent-capabilities-automate-sales-order-taking-process).

### Directions EMEA 2024

Directions EMEA 2024 will take place from November 6-8 in Vienna. Directions EMEA is the premier event for Dynamics partners to gather and share insights on the future of the industry. The conference focuses on helping the SMB market unlock its full potential in technical, business development and strategy with ERP, CRM, and Cloud solutions, including Microsoft Dynamics 365 Business Central. Learn more and register at

To learn more about this event and to register, visit [Directions EMEA 2024](https://www.directionsforpartners.com/conferences-and-events/directions/emea-2024).

### Features becoming mandatory soon

Prepare for features becoming mandatory soon. Learn more in [Optional features that are now mandatory](https://aka.ms/BCFeatureMgmt).

When the following features become mandatory, they might have potentially disruptive effects on extensions and apps you install in the future. These features are now optional to use and can be enabled in the **Feature Management** page in Business Central. Learn in more [Enabling Upcoming Features Ahead of Time](../administration/feature-management.md)).

- **Extending G/L Entry Aggregations When Posting Invoices**

   This feature is generally available with Update 23.1 and becoming mandatory in Update 26.0 (2025 release wave 1). The Invoice Posting interface replaces the use of the **Invoice Post. Buffer** table. The replacement helps resolve extensibility issues for the legacy Invoice Post. Buffer table. You can now use your own implementation of G/L invoice posting. As a developer, you can learn more about how to extend G/L entry aggregations when posting invoices [Extending G/L Entry Aggregations When Posting Invoices](../developer/devenv-invoice-posting-example.md).

- **New extensible exchange rate adjustment**

   This feature, including the posting review feature, is generally available with Update 23.0 and becoming mandatory in Update 26.0 (2025 release wave 1). New capability replaces the legacy Exchange Rates Adjustment Report. This new capability increases extensibility and makes it easier to comply with local and industry-specific requirements. It also gives you more control over exchange rate adjustments with a posting preview and how dimension values are post when you adjust exchange rate, and better reporting. As a developer, you can learn more about how to extend G/L entry aggregations when posting invoices in [Extending Currency Exchange Rate Adjustments](../developer/devenv-extend-exchange-rates.md).

Before the features become mandatory, work with your partner to update installed extensions and apps.

### Discover all partner related resources

Are you a partner who wants a list of relevant resources? Learn more in [Resources for Partners](https://aka.ms/BCAll).

### Discover all user related resources

Are you a user who wants a list of relevant resources? Learn more in [Resources for users](https://aka.ms/BCUsers).  
