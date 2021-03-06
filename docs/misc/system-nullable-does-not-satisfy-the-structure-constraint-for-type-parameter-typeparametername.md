---
title: "“System.Nullable”不满足类型形参“&lt;typeparametername&gt;”的“Structure”约束 | Microsoft Docs"
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
  - "bc32115"
  - "vbc32115"
helpviewer_keywords: 
  - "BC32115"
ms.assetid: 98053645-fa76-4826-a7c1-f1bdf3511863
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “System.Nullable”不满足类型形参“&lt;typeparametername&gt;”的“Structure”约束
将 <xref:System.Nullable%601> 类型实参传递给具有 `Structure` 约束的类型形参时调用了泛型类型。  
  
 公共语言运行时 \(CLR\) 明确禁止将 <xref:System.Nullable%601> 结构用作其自身的类型实参。 即使它是结构并且在其他方面满足 `Structure` 约束，使用它也可能会以递归方式导致繁琐的构造（如 `Nullable(Of Nullable(Of Nullable))`）。  
  
 **错误 ID：**BC32115  
  
### 更正此错误  
  
-   从类型形参中删除 `Structure` 约束，或将类型实参更改为 <xref:System.Nullable%601> 以外的某种值类型。  
  
## 请参阅  
 <xref:System.Nullable%601>   
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [结构 \(Visual Basic\)](http://msdn.microsoft.com/zh-cn/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)