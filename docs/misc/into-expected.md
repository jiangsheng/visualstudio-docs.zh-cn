---
title: "应为“Into” | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36615"
  - "vbc36615"
helpviewer_keywords: 
  - "BC36615"
ms.assetid: 24062dd9-a973-43b6-88d3-c11adc5a3736
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 应为“Into”
`Aggregate`、`Group By` 或 `Group Join` 子句已被指定，但没有使用 `Into` 运算符。 使用 `Into` 运算符标识要对查询结果应用的聚合函数，并标识要包含分组结果的查询结果类型的成员（通过使用 `Group` 聚合函数）。  
  
 **错误 ID：**BC36615  
  
### 更正此错误  
  
1.  将 `Into` 运算符添加到 `Aggregate`、`Group By` 或 `Group Join` 子句。 下面是一个示例：  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## 请参阅  
 [Aggregate 子句](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Group By 子句](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Group Join 子句](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Visual Basic 中的 LINQ 简介](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)