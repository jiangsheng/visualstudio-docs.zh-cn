---
title: "类型实参不能应用于表达式“&lt;expression&gt;” | Microsoft Docs"
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
  - "bc32058"
  - "vbc32058"
helpviewer_keywords: 
  - "BC32058"
ms.assetid: c6b9b49c-6fb2-47b8-a8bb-464562d3adfd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型实参不能应用于表达式“&lt;expression&gt;”
使用 [Of](/dotnet/visual-basic/language-reference/statements/of-clause) 子句定义导入别名，该子句可将类型实参传递给导入别名。  
  
 类型实参用于泛型类型，只有类、结构、接口、过程和委托可以为泛型。 命名空间和导入别名都不能为泛型。  
  
 **错误 ID:** BC32058  
  
### 更正此错误  
  
-   删除 `Of` 子句和导入别名中的类型实参。  
  
## 请参阅  
 [Imports 语句（.NET 命名空间和类型）](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)   
 [引用和 Imports 语句](/dotnet/visual-basic/programming-guide/program-structure/references-and-the-imports-statement)   
 [NOTINBUILD：当多个变量具有相同名称时解析引用](http://msdn.microsoft.com/zh-cn/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)