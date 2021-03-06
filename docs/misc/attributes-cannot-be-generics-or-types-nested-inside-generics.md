---
title: "特性不能是泛型或泛型内部嵌套的类型 | Microsoft Docs"
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
  - "bc32067"
  - "vbc32067"
helpviewer_keywords: 
  - "BC32067"
ms.assetid: 93ae2848-0a72-4ae5-82a3-32e0a49bb7cd
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 特性不能是泛型或泛型内部嵌套的类型
声明为泛型类型的特性，或在泛型类型中声明的特性。  
  
 Visual Basic 和 .NET Framework 当前不支持特性和泛型类型的任意组合。 这意味着会受到以下限制：  
  
-   特性不能是泛型类型，也不能在泛型类型中声明特性。  
  
-   特性不能从泛型类继承，而泛型类也不能从特性继承。  
  
-   应用特性时，不能提供属于以下任何类型的参数：  
  
    -   泛型类型，  
  
    -   从泛型类型构造的类型，  
  
    -   包含类型的类型参数，或  
  
    -   从包含类型的类型参数构造的类型。  
  
 **错误 ID：**BC32067  
  
### 更正此错误  
  
-   如果特性声明中包含 `Of` 关键字和类型参数列表，则将其删除。  
  
-   如果特性声明出现在泛型类型中，则将其移动到任何泛型类型之外。  
  
## 请参阅  
 <xref:System.Attribute>   
 [不在生成中：Visual Basic 中的特性概述](http://msdn.microsoft.com/zh-cn/0d0cff64-892d-4f57-83bd-bef388553d4f)   
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)