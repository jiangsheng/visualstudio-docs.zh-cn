---
title: "“Sub New”无法处理事件 | Microsoft Docs"
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
  - "vbc30497"
  - "bc30497"
helpviewer_keywords: 
  - "BC30497"
ms.assetid: b8a546c4-914e-49de-b553-9fc0f41424ed
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Sub New”无法处理事件
你试图将 `Sub New` 与 `Handles` 组合在一起，这样做无效。 在过程声明的结尾使用 `Handles` 关键字，以使其处理由使用 `WithEvents` 关键字声明的对象变量引发的事件。  
  
 **错误 ID：**BC30497  
  
### 更正此错误  
  
1.  请不要在此上下文中使用 `New`。  
  
## 请参阅  
 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause)   
 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [WithEvents](/dotnet/visual-basic/language-reference/modifiers/withevents)