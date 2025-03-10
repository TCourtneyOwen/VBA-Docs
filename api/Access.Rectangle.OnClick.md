---
title: Rectangle.OnClick property (Access)
keywords: vbaac10.chm10300
f1_keywords:
- vbaac10.chm10300
ms.prod: access
api_name:
- Access.Rectangle.OnClick
ms.assetid: 7b0802ec-3320-44fc-09b5-8f6ed65c32de
ms.date: 02/22/2019
ms.localizationpriority: medium
---


# Rectangle.OnClick property (Access)

Sets or returns the value of the **On Click** box in the Properties window. Read/write **String**.


## Syntax

_expression_.**OnClick**

_expression_ A variable that represents a **[Rectangle](Access.Rectangle.md)** object.


## Remarks

This property is helpful for programmatically changing the action that Microsoft Access takes when an event is triggered. For example, between event calls you may want to change an expression's parameters, or switch from an event procedure to an expression or macro, depending on the circumstances under which the event was triggered. 

The **Click** event occurs when a user presses and releases the left mouse button over an object.

The **OnClick** value will be one of the following, depending on the selection chosen in the Choose Builder window (accessed by choosing the **Build** button next to the **On Click** box in the object's Properties window):

- If you choose Expression Builder, the value will be =_expression_, where _expression_ is the expression from the Expression Builder window.
    
- If you choose Macro Builder, the value is the name of the macro. 
    
- If you choose Code Builder, the value will be [Event Procedure]. 
    
If the **On Click** box is blank, the property value is an empty string.


## Example

The following example associates the **Click** event with the **OK_Click** event procedure for the button named **OK** on the **Order Entry** form, if there is currently no association.


```vb
With Forms("Order Entry").Controls("OK") 
 If .OnClick = "" Then 
 .OnClick = "[Event Procedure]" 
 End If 
End With 

```


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]