---
title: OnGetFilename Event
description: Learn about the OnGetFilename event in Business Central.  
ms.date: 06/11/2025
ms.topic: article
author: jswymer
---
# OnGetFilename event

This article describes the syntax of the `OnGetFilename` event and the attributes of the report payload.

## Usage

The `OnGetFilename` event lets you set the filename that's suggested or used when you export a report, like to PDF, Excel, or Word. Subscribe to this event to use your own logic for naming exported report files, like adding the date, customer name, or other details, instead of the default filename.

Use this event to:

- Make filenames more descriptive or user friendly.
- Meet business or compliance requirements for file naming.
- Avoid filename conflicts when you export multiple reports.

## Publisher

Codeunit **44 ReportManagement**.

## Raised

When the user selects **Print**, **Preview**, or one of the **Send to** actions except **Schedule** on a report request page.

## Event signature

```AL
[IntegrationEvent(false, false)]
local procedure OnGetFilename(ReportID: Integer; Caption: Text[250]; ObjectPayload: JsonObject; FileExtension: Text[30]; ReportRecordRef: RecordRef; var Filename: Text; var Success: Boolean)
```

## Event subscriber syntax

```AL
[IntegrationEvent(false, false)]
local procedure OnGetFilename(ReportID: Integer; Caption: Text[250]; ObjectPayload: JsonObject; FileExtension: Text[30]; ReportRecordRef: RecordRef; var Filename: Text; var Success: Boolean)
```

## Parameters

*ReportID*

Type: [Integer](methods-auto/integer/integer-data-type.md)

The ID of the report object.

*ObjectPayload*

Type: [JsonObject](methods-auto/jsonobject/jsonobject-data-type.md)

Instance of the report payload. Learn more in [Report payload structure](#reportpayload).

*FileExtension*

Type: [Text](methods-auto/text/text-data-type.md)

Specifies the file extension of the saved report, like .pdf, .docx, or .xlsx.

*Success*

Type: [Boolean](methods-auto/boolean/boolean-data-type.md)

Specifies whether the extension handled the action successfully.

[!INCLUDE[report_payload_md](includes/report_payload.md)]

## Example

This AL code subscribes to the `OnGetFilename` event to customize the filename with the current date when you save a report as a PDF.

```AL
codeunit 50100 MyFilenameSubscriber
{
    [EventSubscriber(ObjectType::Codeunit, Codeunit::ReportManagement, 'OnGetFilename', '', false, false)]
    local procedure OnGetFilenameHandler(ReportID: Integer; Caption: Text[250]; ObjectPayload: JsonObject; FileExtension: Text[30]; ReportRecordRef: RecordRef; var filename: Text; var Success: Boolean)
    begin
        // Check if this is the "Customer - Top 10 List" report and PDF export
        if (FileExtension = '.pdf') then begin
            Filename := Caption + '_' + Format(Today, 0, '<Year>-<Month>-<Day>');
            Success := true; // Mark as handled to prevent the default filename logic

        end;
    end;
}
```

> [!TIP]
> For a more complex example of how to use this event, see codeunit **1890 "Reminder Communication"** in the Business Central base application.

## Related information

[Working With and Troubleshooting Payloads](devenv-reports-troubleshoot-printing.md)  
[Developing Printer Extensions Overview](devenv-reports-printing.md)  
[Creating a Printer Extension](devenv-reports-create-printer-extension.md)  
[Events in AL](devenv-events-in-al.md)  
[Publishing Events](devenv-publishing-events.md)  
[Raising Events](devenv-raising-events.md)  
[Subscribing to Events](devenv-subscribing-to-events.md)  
