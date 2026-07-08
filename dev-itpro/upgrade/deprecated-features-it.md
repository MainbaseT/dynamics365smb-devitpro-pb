---
title: Italian features that are moved, removed, or replaced | Microsoft Docs
description: We're constantly streamlining and adjusting our app in-step with market developments. Read about the features for Italy that we have moved, removed, or replaced.
author: bholtorf
ms.topic: reference
ms.devlang: al
ms.search.keywords: deprecated, Italy, local functionality
ms.date: 07/02/2026
ms.author: jswymer
ms.reviewer: jswymer
---

# Deprecated features in the Italian version of [!INCLUDE [prod_long](../developer/includes/prod_long.md)]
This article lists and describes the local functionality for Italy that has been removed from [!INCLUDE[prod_short](../developer/includes/prod_short.md)], made available from a new page or report, or replaced by a new feature.

[!INCLUDE [feature-deprecation](../includes/feature-deprecation.md)]

## Changes in 2025 release wave 2

The following objects are marked as `ObsoleteState = Pending` in version 27.0 and will be removed in a future version.

### Italian Subcontracting functionality replaced by the Subcontracting app

|Moved, Removed, or Replaced? |    Why?|
|-----------------------------|-----|
|Replaced| The Italy-specific subcontracting functionality is replaced by the **Subcontracting** app, which ships as a separate extension and is available for all countries/regions.<br><br>The Italian version included dedicated subcontracting capabilities such as subcontracting orders, subcontracting transfer orders, subcontractor price lists, and WIP-item tracking between main contractors and subcontractors. These capabilities are now provided by the Subcontracting app, which offers the same functionality with additional capabilities including item tracking and warehouse handling in the purchase flow, item charges for subcontracting, and easier navigation between production order, purchase and tranfer orders.<br><br>The following Italy-specific objects are marked as `ObsoleteState = Pending` in version 27.0:<ul><li>**Subcontracting Order** and **Subcontracting Order List** pages</li><li>**Subcontr. Transfer Order** and related subform pages</li><li>**Subcontracting Transfer List** page</li><li>**Subcontracting Prices** page and **Subcontractor Prices** table</li><li>**Create Subcontr.Transf. Order** report</li><li>**Create Subcontr. Return Order** report</li><li>**Subcontract. Transfer Shipment** report</li><li>**Subcontr. Dispatching List** report</li><li>**Subcontracting Management** and **Subcontracting Prices Mgt.** codeunits</li></ul><br><br>A **Legacy Subcontracting** toggle on the **Manufacturing Setup** page lets environments continue using the old functionality during the transition period. When the Subcontracting app is installed, environments can disable the toggle and migrate to the new app. Partners with extensions that reference the obsoleted objects should take a dependency on the Subcontracting app and update references accordingly.<br><br>Learn more about the Subcontracting app in [Subcontracting overview](/dynamics365/business-central/production-how-to-subcontract-manufacturing). Learn more about the Italian subcontracting functionality being replaced in [Italian Subcontracting](/dynamics365/business-central/LocalFunctionality/Italy/italian-subcontracting).<br><br>An **IT Subcontracting Migration** app is available to migrate open data from the legacy Italian subcontracting to the Subcontracting app. The migration runs in sandbox environments only and requires that both the Subcontracting app and the IT Migration app are installed. It migrates vendors, purchase orders/lines, transfer orders/lines, production order components and routing lines, routing lines (master data), and subcontractor prices. Before you run the migration, complete all open WIP transfer orders and related purchase orders. The migration is irreversible and locks the affected tables during the process. Historical and posted data isn't migrated. Production environment support is planned for a later release.|

## Report trade with customers and vendors in blocked countries/regions

You must submit a periodic report of transactions with customers and vendors in certain countries/regions that the Italian government has identified in a block list.

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Removed| The functionality for blocked countries/regions is removed from the Italian version.|

## Multiple interest rates

When you create finance charge terms and reminder terms, for delayed payment penalty, you can specify multiple interest rates so that the penalty fee is calculated from different interest rates in different periods.

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Moved| The Multiple Interest Rates feature is no longer specific to Italy. We've made it generally available in the standard product. |

## Fields marked as ObsoleteState:Pending

[!INCLUDE [fields-obsolete-it](../includes/fields-obsolete-it.md)]

## Related information

[Deprecated Features in the Base App](deprecated-features-w1.md)  
[Deprecated Features in the Platform - Clients, Server, and Database](deprecated-features-platform.md)  
[Upgrading to Business Central](upgrading-to-business-central.md)  
[Upgrading the Application Code](upgrading-the-application-code.md)  
[Deprecated Fields, and Fields Marked as Obsolete](deprecated-fields.md)  
[Italy Local Functionality](/dynamics365/business-central/LocalFunctionality/Italy/italy-local-functionality)  
