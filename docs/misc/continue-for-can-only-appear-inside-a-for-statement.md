---
title: "&quot;Continue For&quot; 只能出现在 &quot;For&quot; 语句内 | Microsoft Docs"
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
  - "bc30783"
  - "vbc30783"
helpviewer_keywords: 
  - "BC30783"
ms.assetid: 70891018-27c8-4d36-b168-8cc7177d70cb
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Continue For&quot; 只能出现在 &quot;For&quot; 语句内
`Continue For` 语句只能出现在 `For...Next` 循环内。  
  
 **错误 ID：**BC30783  
  
### 更正此错误  
  
1.  如果 `Continue For` 语句在 `Do...Loop` 中，请将该语句更改为 `Continue Do`。  
  
     \- 或 \-  
  
     如果 `Continue For` 语句在 `While...End While` 循环中，请将该语句更改为 `Continue While`。  
  
2.  否则，请删除 `Continue For` 语句。  
  
## 请参阅  
 [Continue 语句](/dotnet/visual-basic/language-reference/statements/continue-statement)   
 [For...Next 语句](/dotnet/visual-basic/language-reference/statements/for-next-statement)