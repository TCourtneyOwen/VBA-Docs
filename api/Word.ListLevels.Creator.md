---
title: ListLevels.Creator property (Word)
keywords: vbawd10.chm160302057
f1_keywords:
- vbawd10.chm160302057
ms.prod: word
api_name:
- Word.ListLevels.Creator
ms.assetid: b349e652-b3fa-1a0c-ba81-7331f185c26b
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# ListLevels.Creator property (Word)

Returns a 32-bit integer that indicates the application in which the specified object was created. Read-only **Long**.


## Syntax

_expression_.**Creator**

_expression_ Required. A variable that represents a '[ListLevels](Word.listlevels.md)' collection.


## Remarks

If the object was created in Microsoft Word, the **Creator** property returns the hexadecimal number 4D535744, which represents the string "MSWD." This property was primarily designed to be used on the Macintosh, where each application has a four-character creator code. For example, Microsoft Word has the creator code MSWD. For additional information about this property, consult the language reference Help included with Microsoft Office Macintosh Edition.


## See also


[ListLevels Collection Object](Word.listlevels.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]