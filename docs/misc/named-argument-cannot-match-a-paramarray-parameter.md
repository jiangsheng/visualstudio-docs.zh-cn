---
title: "命名参数无法匹配 ParamArray 参数 | Microsoft Docs"
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
  - "bc30587"
  - "vbc30587"
helpviewer_keywords: 
  - "BC30587"
ms.assetid: aff179af-96f2-4157-971e-881d8e08f5f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 命名参数无法匹配 ParamArray 参数
你提供了一个命名参数（由参数中后接冒号和等号的声明名称指定，后跟参数值）；但是你不能按名称传递参数数组。 在调用过程时，你向参数数组提供以逗号分隔的不定量参数，且编译器无法将多个参数与单个名称相关联。  
  
 **错误 ID：**BC30587  
  
### 更正此错误  
  
-   按位置传递参数，而不是按名称。  
  
## 请参阅  
 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray)   
 [按位置和按名称传递参数](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)