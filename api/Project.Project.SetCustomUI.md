---
title: Project.SetCustomUI method (Project)
keywords: vbapj.chm131080
f1_keywords:
- vbapj.chm131080
ms.prod: project-server
api_name:
- Project.Project.SetCustomUI
ms.assetid: d4dd1b08-8f74-1d55-bc53-dc44744415af
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Project.SetCustomUI method (Project)

Sets the internal XML value for a custom ribbon user interface of the project.


## Syntax

_expression_. `SetCustomUI`( `_CustomUIXML_` )

 _expression_ An expression that returns a **[Project](project.project.md)** object.


## Parameters



|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _CustomUIXML_|Required|**String**|Valid XML data for modifying the ribbon.|

## Return value

 **Nothing**


## Remarks

Because Project uses a binary file format, the **SetCustomUI** method is required for programmatically customizing the ribbon.


> [!NOTE] 
> The **SetCustomUI** method affects all customizations within the scope of the project. For example, if there is an existing customization in the enterprise global project or the local Global.mpt project, to make an additional customization, you must include the existing XML definition in the CustomUIXML argument.

The  _CustomUIXML_ value must be valid XML for Microsoft Office custom ribbon content. The XML value must begin with the **mso:customUI** element, followed by the **mso:ribbon** element. If the **mso:ribbon** element is empty, **SetCustomUI** removes ribbon customizations.

There are several articles about customizing the ribbon for the Fluent user interface in Microsoft Office applications. For more information, see [Overview of the Office Fluent ribbon](../Library-Reference/Concepts/overview-of-the-office-fluent-ribbon.md).


## Example

The following example adds **New Tab** to the left of the **VIEW** tab in the ribbon. **New Tab** contains a group named **New Group**. The button in the group is named **Test Button** and uses the image named **GetExternalDataFromText** in the built-in Microsoft Office icon library.


```vb
Sub AddCustomUI() 
    Dim customUiXml As String 
 
    customUiXml = "<mso:customUI xmlns:mso=""http://schemas.microsoft.com/office/2009/07/customui"">" _
        & "<mso:ribbon><mso:tabs><mso:tab id=""myTab"" label=""New Tab"" " _
        & "insertBeforeQ=""mso:TabView"">" _ 
        & "<mso:group id=""group1"" label=""New Group"">" _ 
        & "<mso:button id=""button1"" label=""Test Button"" size=""large"" " _
        & "imageMso=""GetExternalDataFromText"" />" _ 
        & "</mso:group></mso:tab></mso:tabs></mso:ribbon></mso:customUI>" 
 
    ActiveProject.SetCustomUI (customUiXml) 
End Sub
```

The following example removes all ribbon customizations, because the **mso:ribbon** element is empty.




```vb
Sub RemoveCustomUI() 
    Dim customUiXml As String 
 
    customUiXml = "<mso:customUI xmlns:mso=""http://schemas.microsoft.com/office/2009/07/customui"">" _
        & "<mso:ribbon></mso:ribbon></mso:customUI>" 
 
    ActiveProject.SetCustomUI (customUiXml) 
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]