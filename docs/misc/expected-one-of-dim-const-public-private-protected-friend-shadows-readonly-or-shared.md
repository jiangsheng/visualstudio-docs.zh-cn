---
title: "应为“Dim”、“Const”、“Public”、“Private”、“Protected”、“Friend”、“Shadows”、“ReadOnly”或“Shared”中的一个 | Microsoft Docs"
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
  - "bc30195"
  - "vbc30195"
helpviewer_keywords: 
  - "BC30195"
ms.assetid: 95684eaa-5aa2-4ae4-9a73-5f97c491e02c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 应为“Dim”、“Const”、“Public”、“Private”、“Protected”、“Friend”、“Shadows”、“ReadOnly”或“Shared”中的一个
声明语句中缺少声明关键字。 一个可能的原因是，特性声明调用了方法。  
  
 **错误 ID：**BC30195  
  
### 更正此错误  
  
1.  检查是否在特性声明的内部声明了方法。  
  
2.  在该语句开始处使用适当的声明关键字。  
  
## 请参阅  
 [已声明的元素](/dotnet/visual-basic/programming-guide/language-features/declared-elements/index)   
 [不能用“New”声明数组](../misc/arrays-cannot-be-declared-with-new.md)