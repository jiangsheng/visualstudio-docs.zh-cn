---
title: "Option Strict On 不允许在 lambda 表达式和委托“&lt;delegatename&gt;”之间的隐式类型转换中进行收缩。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36662"
  - "vbc36662"
helpviewer_keywords: 
  - "BC36662"
ms.assetid: 4504497b-56ba-4631-ad7b-59975f7fee04
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On 不允许在 lambda 表达式和委托“&lt;delegatename&gt;”之间的隐式类型转换中进行收缩。
启用 `Option Strict` 时，你不能在委托中参数的数据类型与分配给该委托类型的变量的 lambda 表达式的相应参数之间进行收缩转换。 例如，在下面的代码中，委托 `Del` 具有一个 `Integer` 类型的参数。  
  
```vb#  
Delegate Function Del(ByVal p As Integer) As String  
```  
  
 因此，分配给 `Del` 类型的变量的任何 lambda 表达式的相应参数可为 `Integer` 或任何数据类型，以确保存在 `Integer` 的扩大转换。  
  
```vb#  
' Valid. Dim example1 As Del = Function(n As Integer) "Valid" Dim example2 As Del = Function(n As Long) "Valid" ' Not valid. Dim example3 As Del = Function(n As Short) "Not Valid"  
```  
  
 **错误 ID：**BC36662  
  
### 更正此错误  
  
-   更改委托或 lambda 表达式中的参数的数据类型，以便所需的扩大关系存在。  
  
-   请勿指定 Lambda 表达式中的参数数据类型。 将从委托中的相应参数推断类型。  
  
    ```vb#  
    Dim example4 As Del = Function(n) "Valid"  
    ```  
  
## 请参阅  
 [lambda 表达式](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [委托](/dotnet/visual-basic/programming-guide/language-features/delegates/delegates)   
 [扩大转换和收缩转换](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [宽松委托转换](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)