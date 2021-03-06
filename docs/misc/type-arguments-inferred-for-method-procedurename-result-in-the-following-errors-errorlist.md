---
title: "为方法 “&lt;procedurename&gt;” 推理出的类型参数导致以下错误：&lt;errorlist&gt; | Microsoft Docs"
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
  - "bc30954"
  - "vbc30954"
helpviewer_keywords: 
  - "BC30954"
ms.assetid: 796592c4-70b7-45be-9322-db09e9095d7d
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 为方法 “&lt;procedurename&gt;” 推理出的类型参数导致以下错误：&lt;errorlist&gt;
未提供任何类型参数就调用了泛型过程，并且推导出的类型变量将导致一个或多个约束冲突。  
  
 通常，在调用某个泛型类型时，要为该泛型类型定义的每个类型形参提供一个类型实参。 如果未提供任何类型实参，编译器将尝试推断要传递给类型形参的类型。 如果推导出的类型未能满足一个或多个类型参数约束，编译器将生成此错误。  
  
 类型形参上的*约束*限制可传递到此类型参数的类型实参。 例如，类型形参可能会被约束为实现 <xref:System.IComparable%601> 接口的类。 有关详细信息，请参见 [Visual Basic 中的泛型过程](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures) 中的“约束”。  
  
 **错误 ID：**BC30954  
  
### 更正此错误  
  
-   为泛型过程提供类型实参，以使编译器不对它们进行推断。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Visual Basic 中的泛型过程](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)