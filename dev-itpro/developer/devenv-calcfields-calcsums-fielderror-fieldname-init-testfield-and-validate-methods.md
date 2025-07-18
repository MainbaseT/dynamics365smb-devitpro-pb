---
title: Field calculation methods
description: CalcFields, CalcSums, FieldError, FieldName, Init, TestField, and Validate Methods in Business Central.
ms.date: 01/14/2025
ms.update-cycle: 1095-days
ms.topic: how-to
author: SusanneWindfeldPedersen
ms.author: solsen
ms.reviewer: solsen
ms.custom: evergreen
---

# Field calculation methods

The following methods perform various actions on fields:  

- [CalcFields](methods-auto/record/record-calcfields-method.md)
- [CalcSums](methods-auto/record/record-calcsums-method.md)
- [FieldError](methods-auto/fieldref/fieldref-fielderror-string-method.md)
- [FieldName](methods-auto/record/record-fieldname-method.md)
- [Init](methods-auto/record/record-init-method.md)
- [TestField](methods-auto/record/record-testfield-joker-method.md)
- [Validate](methods-auto/record/record-validate-method.md)

## CalcFields method

CalcFields updates FlowFields. FlowFields are automatically updated when they're the direct source expressions of controls, but they must be explicitly calculated when they're part of a more complex expression. For more information about Flowfields, see [FlowFields](devenv-flowfields.md).  

CalcFields has the following syntax.  

```AL  
[Ok :=] Record.CalcFields(Field1, [Field2],...);  
```  

When you use FlowFields in AL methods, you must use the CalcFields method to update them.  

In the following example, the SETRANGE method sets a filter and then the CalcFields method calculates the Balance and Balance Due fields by using the current filter and performing the calculations that are defined as the CalcFormula properties of the FlowFields.

```AL  
var  
  Customer: Record Customer;

Customer.Get('01454545');  
Customer.SetRange("Date Filter",0D,TODAY);  
Customer.CalcFields(Balance,"Balance Due");  
Message('The Balance is %1 and your Balance Due is %2',Customer.Balance,Customer."Balance Due");  
```  

The following message is displayed:  

**The Balance is 342,529.44 and your Balance Due is 342,529.44**  

## CalcSums method

CalcSums calculates the sum of one or more fields that are SumIndexFields in the record.  

CalcSums has the following syntax.  

```AL
[Ok :=] Record.CalcSums (Field1, [Field2],...);  
```  

For CalcSums, a key that contains the SumIndexFields must be selected as the current key. Similar to CalcFields, CalcSums uses the current filter settings when it performs the calculation.  

In the following example, an appropriate key is selected, some filters are set, the calculation is performed and then a message is displayed.

```AL  
var  
  custledgerentry: Record "Cust. Ledger Entry";

custledgerentry.SetCurrentKey("Customer No.");  
custledgerentry.SetRange("Customer No.",'10000','50000');  
custledgerentry.SetRange("Posting Date",0D,TODAY);  
custledgerentry.CalcSums("Sales (LCY)");  
Message('%1 calculated sales',custledgerentry."Sales (LCY)");  
```  

## FieldError method

FieldError triggers a runtime error after it displays a field-related error message.  

FieldError has the following syntax.  

```AL  
Record.FieldError(Field, [Text]);  
```  

This method is similar to the Error method. However, in the FieldError method, if the name of a field is changed, for example, translated to another language, in the Table Designer, the message from the FieldError method reflects the current name of the field.  

The following examples show how to use the FieldError method.

```AL
var 
  Item: Record Item;

Item.Get('70000');  
If Item.Class <> 'HARDWARE' then  
   Item.FieldError(Class);  
```  

If item 70000 has a Class other than HARDWARE, then you receive the following error message:  

**Class must not be OTHER in Item No. ='70000'.**  

If the text or code field contains the empty string, then you receive the following error message:  

**You must specify Class in Item No.='70000'.**  

If the field is a numeric field and is empty, it's treated as if it contains the value 0 (zero), and then you receive the following error message:  

**Class must not be 0 in Item No.='70000'.**  

You can change the default text that is displayed in the error message. The following example shows how to use the FieldError method and change the default text. This example requires that you create the following variable.  

|Variable|Data type|  
|--------|---------|  
|Class|Code|  

```AL  
var  
  Class: Code[30];

if Item.Class < '4711' then
   Item.FieldError(Class,'must be greater than 4711');  
```  

The following error message is displayed:  

**Class must be greater than 4711 in Item No.='70000'.**  

## FieldName  

FieldName returns the name of a field. It has the following syntax.  

```AL  
Name := Record.FieldName(Field);  
```  

You could just use the name of the field. However, using FieldName lets you create messages that always contain the name of the field, even if the name of the field is changed.  

This example shows how to use FieldName together with FieldError.  

```AL  
FieldError(Quantity,'must not be less than ' + FieldName("Quantity Shipped"));  
```  

## Init

Init initializes a record. It has the following syntax.  

```AL  
Record.Init();
```  

If a default value for a field has been defined by using the **InitValue** property, this value is used for the initialization. Otherwise, the default value of each data type is used.  

> [!NOTE]  
> Init doesn't initialize the fields of the primary key.

## TestField method

TestField tests whether a field contains a specific value. It has the following syntax.  

```AL  
Record.TestField(Field, [Value]);  
```  

If the test fails, that is, if the field doesn't contain the specified value, an error message is displayed and a run-time error is triggered. This means that any changes that were made to the record are discarded. If the value that you test against is an empty string, the field must have a value other than blank or 0 (zero).  

The following example tests the Language Code field for customer number 10000 in the Customer table and tests whether the Language Code is ZX.

```AL
var
   customer: Record Customer;

customer.Get('10000');  
customer.TestField("Language Code",'ZX');  
```  

## Validate method

Validate calls the OnValidate trigger of a field. It has the following syntax.  

```AL  
Record.Validate(Field [, NewValue]);  
```  

When you enter an account number in a ledger, code in a table trigger is executed to transfer the name of the account from the chart of accounts. If you enter an account number in a batch job, the code which transfers the name of the account isn't automatically executed. The following example executes the appropriate field-level trigger code.  

```AL
var
  GeneralLedgerEntry: Record "G/L Entry";

GeneralLedgerEntry.Validate("G/L AccountNo", '100');  
```  

This corresponds to the following code.  

```AL  
GeneralLedgerEntry."G/L AccountNo" := '100';  
GeneralLedgerEntry.Validate("G/L AccountNo");  
```  

The `Validate` method is useful for centralizing processing, which makes your application easier to maintain.  

For example, if the OnValidate trigger of the Total Amount field performs a calculation that uses values from three other fields as operands, the calculation must be performed again if the contents of any one of these fields changes. You should avoid entering the calculation formula in the OnValidate triggers of each field because this can create errors if the calculation formula has to be changed later and you have to update the code in all the triggers. Instead, you should enter the calculation formula in the OnValidate trigger of only one of the fields and call this trigger code from the OnValidate triggers of the other fields.

## Related information

[AL methods](methods-auto/library.md)  
