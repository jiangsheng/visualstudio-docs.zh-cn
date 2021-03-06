---
title: "不能在没有“New”约束的类型参数上使用“New” | Microsoft Docs"
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
  - "bc32046"
  - "vbc32046"
helpviewer_keywords: 
  - "BC32046"
ms.assetid: 7ec6b52d-6fd5-47a0-b4a2-163bfd3dae35
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 不能在没有“New”约束的类型参数上使用“New”
声明语句使用 [New 运算符](/dotnet/visual-basic/language-reference/operators/new-operator) 子句，该子句将类型参数指定为要创建的类型，并且不使用 `New` 约束声明该类型参数。  
  
 类型形参上的*“约束”*对在创建泛型类型时传递给该类型形参的任何类型实参施加了一项要求。`New` 约束规定类型参数必须公开一个创建代码可访问的无参数构造函数。 这样做可允许声明语句中的 `New` 子句创建该类型的实例。  
  
 **错误 ID：**BC32046  
  
### 更正此错误  
  
-   如果你可以要求类型参数公开一个可访问的无参数构造函数，则将 `New` 约束添加到类型参数的声明中。  
  
-   如果你不能要求类型参数公开一个可访问的无参数构造函数，则将 `New` 子句从声明语句中删除。 你不能保证传递给该类型形参的类型实参允许创建实例。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)