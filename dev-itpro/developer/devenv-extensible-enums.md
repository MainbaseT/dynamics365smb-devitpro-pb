---
title: Extensible Enums
description: Overview of the enumeration type and the concept of extending them.
author: SusanneWindfeldPedersen
ms.date: 05/21/2025
ms.topic: concept-article
ms.author: solsen
ms.collection: get-started
ms.reviewer: solsen
---

# Extensible Enums

An enumeration type, also known as an enum in programming, is a keyword used to declare a type that consists of a set of named constants. The list of named constants is called the enumeration list. Enums can be used as table fields, local and global variables, and parameters.

To declare an `enum` in AL, you must specify an ID and a name. The enumeration list consists of values and each of the values are declared with an ID and a value. The value ID is the ordinal value on the enumeration list and must be unique. When the enum values are displayed in the UI, they're sorted by the order of declaration. In addition, if extension **B** extends extension **A**, the enum values declared in extension **A** are displayed *before* the enum values declared in extension **B**.

The following example shows the declaration of an enum, which can be extended, and has the four values; **None**, **Bronze**, **Silver**, and **Gold**. 

> [!IMPORTANT]  
> Only enums with the [Extensible property](properties/devenv-extensible-property.md) set to **true** can be extended.


```AL
enum 50121 Loyalty
{
    Extensible = true;
    
    value(0; None) { }
    value(1; Bronze) { }
    value(2; Silver) { }
    value(3; Gold)
    {
        Caption = 'Gold Customer';
    }
}
```

> [!NOTE]  
> While enums and enumextension objects have object IDs, these aren't enforced by the license. In previous versions they reused the range for tables, and were checked against the license at deployment time, but this is no longer the case. Uniqueness validation is now enforced during installation, which will fail if an enum object ID clashes with an already installed enum. Thus, as always, it's important that you use object IDs in your assigned range. This is enforced for AppSource apps, but not for per-tenant extensions, or on-premises. The enum doesn't have to use the same ID as the table it's put on.
>
> With [!INCLUDE [prod_short](includes/prod_short.md)] 2023 release wave 1, IntelliSense suggests the **next available enum ordinal value** both when creating new enums, or when extending existing enums.

> [!IMPORTANT]  
> When creating captions for enums, it's important that the caption doesn't contain a comma. Having a comma in the caption, such as `Caption = 'Diamond Level, with bonus'`, can display over multiple lines in the UI. This behavior also causes that the actual value selected by the user in the UI, doesn't correspond to the value, which is saved in the database.
>
> An AppSourceCop warning is triggered if .xlf files contain commas in enum captions. For more information, see [AppSourceCop Warning AS0087](analyzers/appsourcecop-as0087.md).

## Enumextension object

Enums can be extended in order to add more values to the enumeration list in which case the `Extensible` property must be set to `true`. The syntax for an enum extension, which extends the **Loyalty** enum with the value **Diamond**, is shown below.

```AL
enumextension 50130 LoyaltyWithDiamonds extends Loyalty
{
    value(50130; Diamond)
    {
        Caption = 'Diamond Level';
    }
}
```

## Usage

When referencing a defined enum from code, you use the syntax as illustrated below.

`enum Loyalty`

If you want to define an enum as a table field type, use the syntax illustrated below:
 
```AL
field(50100; Loyal; enum Loyalty) {}
```

Or, as a variable:

```AL
var
    LoyaltyLevel: enum Loyalty;
```

In code, you address a specific enum value like in the following example:

```AL
codeunit 50140 EnumUsage
{
    procedure Foo(p: enum Loyalty)
    var
        LoyaltyLevel: enum Loyalty;
    begin
        if p = p::Gold then begin
            LoyaltyLevel := p;
        end;
    end;
}
```

## Example

The following example illustrates how to define an enum extension of `TypeEnum`, using it in a table extension `TableWithRelationExt` and displaying it as a control on a new page.

```AL
enumextension 50133 TypeEnumExt extends TypeEnum
{
    value(10; Resource) { }
}

tableextension 50135 TableWithRelationExt extends TableWithRelation
{
    fields
    {
        modify(Relation)
        {
            TableRelation = if (Type = const (Resource)) Resource;
        }
    }
}

page 50133 PageOnRelationTable
{
    SourceTable = TableWithRelation;
    SourceTableView = where (Type = const (Resource));
    PageType = List;

    layout
    {
        area(Content)
        {
            repeater(MyRep)
            {
                field(Id; Id)
                {
                    ApplicationArea = All;
                }
                field(Type; Type)
                {
                    ApplicationArea = All;
                }
                field(Relation; Relation)
                {
                    ApplicationArea = All;
                }
            }
        }
    }
}
```

> [!TIP]  
> For another example of how to extend the usage of the `TableRelation` property with enums, see [TableRelation Property](properties/devenv-tablerelation-property.md).

### Conversions

Conversion to and from `enum` is more strict than for `Options` in C/SIDE. 

- An enum can be assigned/compared to an enum of the same type. 
- To be backwards compatible, we support conversion to/from any `Option` for now.

Learn about assignment compatibility in [AssignmentCompatibility property](properties/devenv-assignmentcompatibility-property.md).

## Related information

[AL data types](./methods-auto/library.md)  
[TableRelation property](properties/devenv-tablerelation-property.md)  
[Extensible property](properties/devenv-extensible-property.md)  
[Enum data type](methods-auto/enum/enum-data-type.md)  
[AssignmentCompatibility property](properties/devenv-assignmentcompatibility-property.md)
