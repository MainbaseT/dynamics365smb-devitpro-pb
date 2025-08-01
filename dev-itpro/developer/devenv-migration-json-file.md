---
title: Migration JSON file
description: Description of the JSON file for data migration for AL in Business Central.
author: SusanneWindfeldPedersen
ms.date: 05/02/2025
ms.topic: concept-article
ms.author: solsen
ms.reviewer: solsen
---

# Migration JSON file

[!INCLUDE[2019_releasewave2_15.3_onprem](../includes/2019_releasewave2_15.3_onprem.md)]

Data migration allows you to move table and field data between extensions. The `migration.json` file provides a pointer to the ID of an app that one or more tables are moved to. This file allows you to move table and field data from, for example, a code-customization on the base application to an extension of the base application. The `migration.json` file can be added into the app project of an extension that a table is moved from to specify the ID of the app that the table is moved to. It can, for example, be placed at the root of the AL project. The `migration.json` file must be created manually by following the steps and syntax as described below.

In the extension `app.json` file, ensure that `"target": "OnPrem"`. For more information, see [JSON Files](devenv-json-files.md).

## Create the migration.json file

1) In the root folder of the app project that will migrate data to a different app project, choose **New File**.
2) Name the file `migration.json`.
3) Edit the file by adding one or more IDs inside the `"apprules":[]` section, such as:

```json
{ 
    "apprules": [ 
        { 
            "id": "12345678-abcd-abcd-abcd-1234567890ab" 
        } 
    ] 
} 
```
4) Save the `migration.json` file in the project.

You now have the migration file in place for the data migration from one app project to another. The migration file is used for performing the data migration steps. Learn more in [Migrating tables and fields between extensions](devenv-migrate-table-fields.md).

## Related information

[JSON files](devenv-json-files.md)  
[Migrating tables and fields between extensions](devenv-migrate-table-fields.md) 
