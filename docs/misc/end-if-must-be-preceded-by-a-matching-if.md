---
title: "“End If”前面必须是匹配的“If”。 | Microsoft Docs"
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
  - "bc30087"
  - "vbc30087"
helpviewer_keywords: 
  - "BC30087"
ms.assetid: 81c056bb-267e-44ef-9a44-3a41273090ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “End If”前面必须是匹配的“If”。
出现 `End If` 语句而没有相应的 `If` 语句。`End If` 前面必须是 `If` 语句。  
  
 **错误 ID：**BC30087  
  
### 更正此错误  
  
1.  如果此 `If` 块属于一组嵌套的 `If` 块，请确保每个块均已正确终止。  
  
2.  验证 `If` 块中的其他控制结构是否被正确终止。  
  
3.  确保此 `If` 块的格式正确。  
  
## 请参阅  
 [If...Then...Else 语句](/dotnet/visual-basic/language-reference/statements/if-then-else-statement)