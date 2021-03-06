---
title: "编译器错误 CS1930 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1930"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1930"
ms.assetid: d28d2334-825c-4ffc-b9e9-f5d61f44d672
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1930
已声明范围变量“name”  
  
 查询表达式中的范围变量会一直位于范围内，直到该查询表达式终止。 因此，该变量必须具有唯一标识符。  
  
### 更正此错误  
  
1.  为在查询表达式中引入的每个范围变量指定一个唯一名称。  
  
## 示例  
 下面的示例生成 CS1930，因为同时对 `from` 子句中的范围变量和 `let`子句所引入的范围变量使用了标识符 `num`。  
  
```  
// cs1930.cs using System.Linq; class Program { static void Main() { int[] nums = { 0, 1, 2, 3, 4, 5 }; var query = from num in nums let num = 3 // CS1930 select num; } }  
```  
  
## 请参阅  
 [LINQ 查询表达式](/dotnet/csharp/programming-guide/linq-query-expressions/index)