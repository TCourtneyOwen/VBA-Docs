---
title: Fonts.Parent property (PowerPoint)
keywords: vbapp10.chm528002
f1_keywords:
- vbapp10.chm528002
ms.prod: powerpoint
api_name:
- PowerPoint.Fonts.Parent
ms.assetid: 022cb574-2454-7289-0ce7-b16e9970c512
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Fonts.Parent property (PowerPoint)

Returns the parent object for the specified object.


## Syntax

_expression_.**Parent**

_expression_ A variable that represents a [Fonts](PowerPoint.Fonts.md) object.


## Return value

Object


## Example

This example adds an oval containing text to slide one in the active presentation and rotates the oval and the text 45 degrees. The parent object for the text frame is the **Shape** object that contains the text.


```vb
Set myShapes = ActivePresentation.Slides(1).Shapes

With myShapes.AddShape(Type:=msoShapeOval, Left:=50, _
        Top:=50, Width:=300, Height:=150).TextFrame

    .TextRange.Text = "Test text"

    .Parent.Rotation = 45

End With
```


## See also


[Fonts Object](PowerPoint.Fonts.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]