---
title: Update 28.3 for Microsoft Dynamics 365 Business Central 2026 Release Wave 1
description: Get an overview of new and changed capabilities in the 28.3 update of Business Central online, which is part of 2026 release wave 1
ms.author: jswymer
ms.date: 07/01/2026
ms.reviewer: jswymer
ms.topic: concept-article
author: jswymer
ms.custom:
    - bap-template
---
# Update 28.3 for Business Central 2026 release wave 1

Want to know what changes are in update 28.3? The following sections provide an overview and relevant links to hotfixes and regulatory features in this update. In addition, the release notes include some good-to-know information and links that you might find interesting.

## Hotfixes

Learn about the hotfixes and download the on-premises files from Microsoft Support at [Update 28.3 for Business Central 2026 release wave 1](https://support.microsoft.com/help/5105551).

## Feature changes

|Product area|Feature|Public preview/General availability|
|-|-|-|
|Copilot and agents|Assign project in Expense Agent web app<br><br>With project tracking turned on for the Expense Agent, users can specify a project and project task directly in the **Categorization** tab when creating or editing an expense. Learn more in [Set up Expense Agent](/dynamics365/business-central/expense-management/expense-agent-configuration-page).|Public preview|
||[Use Expense Agent in German, Danish, French, and Spanish](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/use-expense-agent-german-danish-french-spanish-languages)|Public preview|
||[Run multiple Sales Order Agents per company with smarter item matching, relevance filtering, and streamlined setup](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/run-multiple-sales-order-agents-per-company-smarter-item-matching-relevance-filtering-streamlined-setup)|General availability|
||Try the Payables Agent for free with no email setup<br><br>The Payables Agent trial mode lets you process 50 invoices free of charge. You can easily start the trial directly from the agent's assisted setup guide, without having to configure an email inbox for handling requests. Learn more in [Try the Payables Agent](/dynamics365/business-central/payables-agent-setup#try-payables-agent-with-free-trial-mode).|General availability|
|Country and regional|[Enable electronic invoicing in France](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/enable-electronic-invoicing-france)|General availability|
|Ecommerce|Sell to business customers on more Shopify plans with B2B company sync<br><br>Market catalogs, payment terms, and B2B order processing are available on all plans, not just the Plus plan. |General availability|
|Electronic documents|[Use payments with the E-Document framework](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/use-payments-e-document-framework)|Public preview|
|Financial management|[Calculate taxes for plastic and sugar](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/calculate-taxes-plastic-sugar)|General availability|
|Governance and administration|[Upload, install, and manage PTEs in the admin center](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/upload-install-manage-ptes-admin-center)<sup>1</sup> |General availability|
|Supply chain management|[Use subcontracting capabilities in production processes](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/use-subcontracting-capabilities-production-processes)|General availability|

<sup>1</sup> This feature is a service feature available independently of the update version.


## Localization updates

|Country/region|Feature|Description|
|-|-|-|
|Germany|eSTATISTIK.CORE XML Export in German Intrastat|Updated German Intrastat reporting to generate XML files compliant with the latest eSTATISTIK.CORE requirements and removed obsolete IDEV-related validations.|
|Mexico	|CFDI Payment Date Validation Fix|Fixed an issue that could cause CFDI payment documents to fail with a "Date is out of range" validation error during payment processing.|
|Switzerland|Swiss Bank Clearing Number Import v3.0|Added support for the new Swiss bank clearing number file format (CSV Version 3.0). Customers can import both the legacy TXT format and the new CSV format without additional setup.|
|Switzerland|Structured Address Support for QR Invoices|Clarified and documented support for fully structured addresses (Street + Building Number) required for Swiss QR invoices.|
|United Kingdom	|Payment Practices Reporting Updates|Enhanced Payment Practices reporting to support updated UK requirements. The solution also introduces a flexible reporting scheme framework for country-specific requirements.|

## Release plan

For a comprehensive overview of what's new and planned for Business Central online for the entire 2026 release wave 1 (release from April 2026 to October 2026), see [Plan and prepare for Dynamics 365 Business Central in 2026 release wave 1](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/planned-features)<!--(https://aka.ms/BCReleasePlan)-->.

## Upgrade to 28.3

### Online customers

- New customers automatically get Business Central version 28.3.
- Existing customers receive a notification when update 28.3 is available so they can schedule the update. For more information, see [Schedule an update](../administration/tenant-admin-center-update-management.md#schedule).

### On-premises customers

The upgrade path depends on your current major version. Select the instructions that match your deployment:

- **Version 28**: Follow the instructions in [Install a Business Central 2026 release wave 1 update](../upgrade/upgrading-cumulative-update-v28.md).
- **Version 27 and earlier**: Learn more about upgrading to version 28 in [Upgrading to Dynamics 365 Business Central 2026 release wave 1](../upgrade/upgrade-overview-v28.md).

## Good to know

## Copilot and agent data movement across geographies

Starting July 1, 2026, Business Central environments on version 28.0 or later in some countries or regions might process Copilot and agent requests in a different Azure geography. You can manage data processing preferences on the **Copilot & agent capabilities** page.

Learn more in [Copilot data movement across geographies](/dynamics365/business-central/ai-copilot-data-movement).

## Expense Agent mobile app preview coming soon

The new Expense Agent mobile app for iOS and Android devices is expected to be available on the Apple App Store and Google Play Store for installation in July 2026. This mobile app enables employees to capture and submit expense reports directly from their devices.

Learn more in [Capture expenses with Expense Agent on your mobile app](/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/capture-expenses-expense-agent-mobile-app).

### Business Central Launch Edition - 2026 release wave 1

Explore the Business Central Launch Edition (BCLE)&mdash;a comprehensive skilling experience designed to help partners stay up to date, aligned, and ready to deliver value faster with every release wave.

- 40+ what's new sessions on YouTube: [aka.ms/BCLE](https://aka.ms/BCLE)
- 'What's new' partner deck for download: [aka.ms/BCLEDECK](https://aka.ms/BCLEDECK)
- Have questions? Go to the new Business Central partner communities on Viva Engage and ask the product experts: [aka.ms/BCVivaEngage](https://aka.ms/BCVivaEngage)

### Discover all partner-related resources

Are you a partner who wants a list of relevant resources? Learn more in [Resources for Partners](https://aka.ms/BCAll).

### Discover all user-related resources

Are you a user who wants a list of relevant resources? Learn more in [Resources for users](https://aka.ms/BCUsers).
