---
title: "Images Property"
description: "Specifies the list of images to include in the control add-in."
ms.author: solsen
ms.date: 02/26/2024
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# Images Property
> **Version**: _Available or changed with runtime version 1.0._

Specifies the list of images to include in the control add-in.

## Applies to
-   Control Add In

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Property values

A list of comma-separated strings that represents paths to image files. The default is blank, with no images being used by the control add-in. 

You can specify multiple files within the same path string by using a combination of a valid literal path and wildcard characters (* and ?). However, it doesn't support regular expressions.

## Remarks

The Images property specifies image resources that are referenced by the control add-in scripts. Any specified images must be of a supported web format and extension, such as .PNG or .GIF. 

Images can be either external resources referenced using a URL or can be embedded within the extension. Embedded images must be added to the extension project folder in Visual Studio Code and referenced using a relative path. At runtime, the path to an embedded can be obtained using the [GetImageResource method](../methods/devenv-getimageresource-method.md) method. Unlike scripts and stylesheets, images are loaded on demand when they're first used in code. Since images are stored in the application after the extension is deployed, it's recommended to keep the number of image files and combined image size to a minimum. 

## Syntax example

```AL
Images = 'https://fabrikam.com/banner.png',
              'images/map.png',
              'images/*.png';
```

## Image paths on control add-ins can be relative to the control add-in source file

[!INCLUDE [2024-releasewave1](../../includes/2024-releasewave1.md)]

Starting from runtime 13, you can store control add-in resources in a location relative to the file that contains the source code of the control add-in. This provides more flexibility in organizing and locating control add-in resources.

When the system needs to locate these resources, it follows a specific search order; first, it looks for the resources in a location relative to the root of the project. If the resources aren't found there, it then searches in a location relative to the source file of the control add-in. 

The following example shows the two options for organizing control add-in resources; scripts, images, and stylesheets. For the file `MyControlAddIn.al`, the resources are organized in two different ways.

### Organizing resources example

For the file `MyControlAddIn.al`.

```al
controladdin MyControlAddIn
{
    Scripts = './js/myscript.js';
    Images = './png/myimage.png';
    StyleSheets = 'css/mystyle.css';
    ...
}
```

The resources are relative to the project root:

```
.
[src]
    MyControlAddIn.al
[resources]
    [js]
        myscript.js
    [png]
        myimage.png
    [css]
        mystyle.css
app.json
```

The resources are relative to the control add-in source:

```
.
[src]
    MyControlAddIn.al
    [resources]
        [js]
            myscript.js
        [png]
            myimage.png
        [css]
            mystyle.css
app.json
```

## See also  

[Control add-in object](../devenv-control-addin-object.md)   