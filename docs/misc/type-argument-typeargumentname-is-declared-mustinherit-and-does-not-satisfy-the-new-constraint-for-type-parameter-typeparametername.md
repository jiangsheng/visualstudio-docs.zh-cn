---
title: "类型实参“&lt;typeargumentname&gt;”声明为“MustInherit”并且不满足类型形参“&lt;typeparametername&gt;”的“New”约束 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32082"
  - "BC32082"
helpviewer_keywords: 
  - "BC32082"
ms.assetid: 597e5944-a61b-4858-ada5-efb80b27f26b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型实参“&lt;typeargumentname&gt;”声明为“MustInherit”并且不满足类型形参“&lt;typeparametername&gt;”的“New”约束
使用 `MustInherit` 类将泛型类型调用为类型实参，而使用 `New` 约束声明相应的类型形参。  
  
 `New` 约束要求在相应类型参数中传递的类型必须支持创建对象。 但是，*“抽象”*类（即声明为 `MustInherit` 的类）不公开任何构造函数，因为你不能从它创建任何对象。  
  
 **错误 ID：**BC32082  
  
### 更正此错误  
  
1.  如果类型参数中使用的类不需要为抽象，则从其声明中删除 `MustInherit` 关键字。  
  
2.  如果在类型参数中使用的类需要为抽象，但不需用于构造泛型类型，则在类型参数中传递一个不同的类。  
  
3.  如果相应的类型参数不需要从传递到它的类型创建任何对象，则从其声明中删除 `New` 约束。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [New 运算符](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)