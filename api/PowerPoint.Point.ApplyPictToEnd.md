---
title: Point.ApplyPictToEnd property (PowerPoint)
ms.prod: powerpoint
api_name:
- PowerPoint.Point.ApplyPictToEnd
ms.assetid: 5b1a3168-9a77-55e0-9d9c-edd66fd338d2
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Point.ApplyPictToEnd property (PowerPoint)

 **True** if a picture is applied to the end of the point or all points in the series. Read/write **Boolean**.


## Syntax

_expression_.**ApplyPictToEnd**

_expression_ A variable that represents a '[Point](PowerPoint.Point.md)' object.


## Example




> [!NOTE] 
> Although the following code applies to Microsoft Word, you can readily modify it to apply to PowerPoint.

The following example applies pictures to the end of all points in the first series of the first chart in the active document. The series must already have pictures applied to it (setting this property changes the picture orientation).




```vb
With ActiveDocument.InlineShapes(1)

    If .HasChart Then

        .Chart.SeriesCollection(1).ApplyPictToEnd = True

    End If

End With
```


## See also


[Point Object](PowerPoint.Point.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]