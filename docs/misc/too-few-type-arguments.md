---
title: "类型实参太少 | Microsoft Docs"
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
  - "vbc36578"
  - "bc36578"
helpviewer_keywords: 
  - "BC36578"
ms.assetid: 881b3009-0c9e-4676-b172-c6aabd14ed14
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 类型实参太少
已调用一个泛型方法，其类型实参少于类型形参。  
  
 在调用泛型方法时，必须为此方法定义的每一个类型形参提供一个类型实参。  
  
 **错误 ID：**BC36578  
  
### 更正此错误  
  
-   向类型实参列表添加类型实参，使所调用泛型方法的每个类型形参都有一个类型实参。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Visual Basic 中的泛型过程](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)