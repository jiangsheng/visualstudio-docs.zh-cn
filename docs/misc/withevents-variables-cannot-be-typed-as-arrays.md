---
title: "“WithEvents”变量不能类型化为数组 | Microsoft Docs"
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
  - "bc30476"
  - "vbc30476"
helpviewer_keywords: 
  - "BC30476"
ms.assetid: 29bed445-a247-4c88-a1eb-115535900377
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “WithEvents”变量不能类型化为数组
你试图使用 `WithEvents` 声明数组。 你可以使用 `WithEvents` 声明任意多个变量，但不能通过这种方式声明数组。  
  
 **错误 ID：**BC30476  
  
### 更正此错误  
  
1.  单独声明变量。  
  
## 请参阅  
 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [不在生成中：WithEvents 和 Handles 子句](http://msdn.microsoft.com/zh-cn/072b9cf6-6298-46f1-849e-4edc1631564c)