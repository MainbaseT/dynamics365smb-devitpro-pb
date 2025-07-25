---
title: Update 24.5 for Microsoft Dynamics 365 Business Central 2024 Release Wave 1
description: Get an overview of new and changed capabilities in the 24.5 update of Business Central online, which is part of 2024 release wave 1.
ms.author: jswymer
ms.date: 09/04/2024
ms.update-cycle: 1095-days
ms.reviewer: jswymer
ms.topic: article
author: jswymer
ms.custom: 
    - bap-template
    - evergreen
---

# Update 24.5 for Microsoft Dynamics 365 Business Central online 2024 release wave 1

Would you like to know what changes are in update 24.5? Below you find an overview and relevant links to what was done on hotfixes and regulatory features in this update. In addition, we gathered some good to know information and links that you might find interesting.

## Hotfixes

Learn about the hotfixes on Microsoft Support at [Update 24.5 for Business Central 2024 Release Wave 1](https://support.microsoft.com/help/5043981). Download the on-premises files from the Microsoft Download Center at [Update 24.5 for Business Cenral](https://www.microsoft.com/en-us/download/details.aspx?id=106245)<!--(https://aka.ms/BCDownload)-->.

## Feature changes

- [Automate country of origin listed for item tracking code in Intrastat reporting (general availability)](/dynamics365/release-plan/2024wave1/smb/dynamics365-business-central/automate-country-origin-listed-item-tracking-code-intrastat-reporting)
- [Enable sustainability features for integrations with APIs (general availability)](/dynamics365/release-plan/2024wave1/smb/dynamics365-business-central/achieving-sustainable-compliance-business-central)
- [Migrate record links and notes with cloud migration tooling (preview)](/dynamics365/release-plan/2024wave1/smb/dynamics365-business-central/migrate-record-links-notes-cloud-migration-tooling)
- [Remove friction when working with external app dependencies (general availability)](/dynamics365/release-plan/2024wave1/smb/dynamics365-business-central/remove-friction-when-working-external-app-dependencies)

## Localization updates

No localization updates for 24.5.

## Release plan

Do you want to get a comprehensive overview of what's new and planned for Business Central online for the entire 2024 release wave 1 (release from April 2024 through September 2024)? Learn more at [Plan and prepare for Dynamics 365 Business Central in 2024 release wave 1](/dynamics365/release-plan/2024wave1/smb/dynamics365-business-central/)<!--(https://aka.ms/BCReleasePlan)-->.

## Upgrade to 24.5

New customers automatically get the latest builds of Business Central (24.5). If you're an existing partner/customer, you receive an email notification as soon as your environment is upgraded.

## Good to know

### Recent service features

The following Business Central online service features were recently rolled out.

- [Manage environment updates more flexibly (preview)](/dynamics365/release-plan/2024wave2/smb/dynamics365-business-central/manage-environment-updates-more-flexibly)

   With this feature, we establish a five-month update period for major updates and the possibility to opt in to minor updates. Learn more in [Major updates and minor updates for Business Central online](../administration/update-rollout-timeline.md).

### Features becoming mandatory soon

Prepare for features becoming mandatory soon. Learn more in [Optional features that are now mandatory](https://aka.ms/BCFeatureMgmt).

When the following features become mandatory, they might have potentially disruptive effects on extensions and apps you install in the future. These features are now optional to use and can be enabled in the **Feature Management** page in Business Central. Learn in more [Enabling Upcoming Features Ahead of Time](../administration/feature-management.md)).

- **Extending G/L Entry Aggregations When Posting Invoices**

   This feature is generally available with Update 23.1 and becoming mandatory in Update 26.0 (2025 Release Wave 1). The Invoice Posting interface replaces the use of the **Invoice Post. Buffer** table. The replacement helps resolve extensibility issues for the legacy Invoice Post. Buffer table. You can now use your own implementation of G/L invoice posting. As a developer, you can learn more about how to extend G/L entry aggregations when posting invoices [Extending G/L Entry Aggregations When Posting Invoices](../developer/devenv-invoice-posting-example.md).

- **New extensible exchange rate adjustment**

   This feature, including the posting review feature, is generally available with Update 23.0 and becoming mandatory in Update 26.0 (2025 Release Wave 1). New capability replaces the legacy Exchange Rates Adjustment Report. This new capability increases extensibility and makes it easier to comply with local and industry-specific requirements. It also gives you more control over exchange rate adjustments with a posting preview and how dimension values are post when you adjust exchange rate, and better reporting. As a developer, you can learn more about how to extend G/L entry aggregations when posting invoices in [Extending Currency Exchange Rate Adjustments](../developer/devenv-extend-exchange-rates.md).

Before the features become mandatory, work with your partner to update installed extensions and apps.

### Discover all partner related resources

Are you a partner who wants a list of relevant resources? Learn more in [Resources for Partners](https://aka.ms/BCAll).

### Discover all user related resources

Are you a user who wants a list of relevant resources? Learn more in [Resources for users](https://aka.ms/BCUsers).  
