---
title: "类型形参“&lt;typeparametername&gt;”的“&lt;genericproceduresignature&gt;”类型实参推理失败 | Microsoft Docs"
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
  - "vbc32051"
  - "bc32051"
helpviewer_keywords: 
  - "BC32051"
ms.assetid: a9c2a0ce-e225-4549-bfd8-d42df5d16bfd
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型形参“&lt;typeparametername&gt;”的“&lt;genericproceduresignature&gt;”类型实参推理失败
类型形参“\<typeparametername\>”的“\<genericproceduresignature\>”类型实参推理失败。 无法从传递给形参“\<parametername\>”的实参推理出类型实参。  
  
 在未提供任何类型实参的情况下调用了泛型过程，编译器无法推断要传递给其中一个形参的类型。  
  
 在调用泛型过程时，通常会为泛型过程所定义的每个类型形参提供类型实参。 如果未提供任何类型实参，则编译器将尝试推断要传递给类型形参的类型。 如果调用的上下文提供与该类型形参冲突的数据类型信息，则类型推理将失败。  
  
 以下代码会生成此错误。  
  
```  
Public Sub doSomething(Of t)(ByVal arg1 As t(), ByVal arg2 As t) End Sub Call doSomething(6, 42)  
```  
  
 在前面的示例中，编译器将根据传递给 `arg2` 的值 42 推断出 `t` 的类型 `Integer`。 但该推断将要求 `arg1` 为类型 `Integer()`，也就是说传递给 `arg1` 的 `Integer` 数组和值 6 与该类型不匹配。  
  
 **错误 ID：**BC32051  
  
### 更正此错误  
  
-   为泛型过程提供类型实参，使编译器无需推断它们。  
  
-   提供与类型实参具有匹配类型的普通实参。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Visual Basic 中的泛型过程](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)