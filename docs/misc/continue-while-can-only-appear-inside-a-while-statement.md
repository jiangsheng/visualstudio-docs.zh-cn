---
title: "“Continue While”只能出现在“While”语句内 | Microsoft Docs"
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
  - "vbc30784"
  - "bc30784"
helpviewer_keywords: 
  - "BC30784"
ms.assetid: b26c77b2-36ae-4dce-b048-f7c4b196faa4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Continue While”只能出现在“While”语句内
`Continue While` 语句只能出现在 `For...Next` 循环内。  
  
 **错误 ID：**BC30784  
  
### 更正此错误  
  
1.  如果 `Continue While` 语句在 `Do...Loop` 循环中，请将该语句更改为 `Continue Do`。  
  
2.  如果 `Continue While` 语句在 `For...Next` 循环中，请将该语句更改为 `Continue For`。  
  
3.  否则，请删除 `Continue While` 语句。  
  
## 请参阅  
 [Continue 语句](/dotnet/visual-basic/language-reference/statements/continue-statement)   
 [While...End While 语句](/dotnet/visual-basic/language-reference/statements/while-end-while-statement)