---
title: Programming in AL
description: AL is the programming language used for manipulating data such as retrieving, inserting, and modifying records in a Business Central database. It controls the execution of the various application objects, such as pages, reports, or codeunits.
ms.date: 01/16/2025
ms.update-cycle: 1095-days
ms.topic: concept-article
author: SusanneWindfeldPedersen
ms.collection: get-started
ms.custom: evergreen
---

# Programming in AL

AL is the programming language that you use to manipulate data, such as retrieving, inserting, and modifying records in a [!INCLUDE [prod_short](includes/prod_short.md)] database. It controls the execution of the various application objects, such as pages, reports, or codeunits. 

By using AL, you can create business rules to ensure that the data stored in the database is meaningful and consistent with the way customers do business. Through AL programming, you can:

- Add new data or transfer data from one table to another, such as from a journal table to a ledger table.
- Combine data from multiple tables into one report or display it on one page.
- Perform calculations, such as calculating the total amount of a sales order.
- Control the flow of the application, such as by showing a message box when a certain condition is met.
- Create new or modify existing objects, such as a page or a report.

## Where to write AL code

Almost every object in [!INCLUDE [prod_short](includes/prod_short.md)] contains triggers where you can add your AL code. Triggers exist for the following objects:

- Tables and table extensions
- Table fields  
- Pages and page extensions
- Reports and report extensions
- Data items
- XMLports  
- Queries  

You can initiate the execution of your AL code in the following ways:  

- Actions  
- Any object that has an instantiation of the object that contains AL code. An example of an instantiation is a variable declaration.  

> [!NOTE]
> If the AL code is in a `local` method, you can't run it from another object.  

## Variable declarations

Declare variables in AL by using the `var` keyword. The syntax looks like this:

```AL
var
        myInt: Integer;
```

If you have multiple variables of the same type, declare them in one line, such as:

```AL
var
        myInt, nextInt, thirdInt : Integer;
        isValid, doCheck : Boolean;
```

Use the `protected` keyword to make variables accessible between tables and table extensions and between pages and page extensions. Learn more in [Protected variables](devenv-protected-variables.md).

## Guidelines for placing AL code  

Use the following guidelines for placing AL code:  

- Generally, write code in codeunits instead of on the object that the code operates on. This approach promotes a clean design and enables code reuse. It also helps enforce security. For example, typically users don't have direct access to tables that contain sensitive data, such as the **General Ledger Entry** table, nor do they have permission to modify objects. If you put the code that operates on the general ledger in a codeunit, provide access for the codeunit to the table, and then give the user permission to run that codeunit. This way, the security of the table isn't compromised and the user can access the table.  

- If you must put code on an object instead of in a codeunit, put the code as close as possible to the object that the code operates on. For example, put code that modifies records in the triggers of the table fields.  

## Reusing code

Reusing code makes developing applications both faster and easier. More importantly, if you organize your AL code as suggested, your applications are less prone to errors. By centralizing the code, you don't unintentionally create inconsistencies by performing the same calculation in many places. For example, you avoid duplicating code in several triggers that have the same table field as their source expression. If you need to change the code, you reduce the risk of forgetting about some of these triggers or making a mistake when you modify one of them.

## Related information

[Simple statements](devenv-al-simple-statements.md)  
[Control statements](devenv-al-control-statements.md)  
[Methods](devenv-al-methods.md)  
[System-defined variables](devenv-system-defined-variables.md)  
[AL operators](devenv-al-operators.md)  
[Developing extensions](devenv-dev-overview.md)  
[Get started with AL](devenv-get-started.md)
