---
title: "&quot;SyncLock&quot; 语句在即时窗口中无效 | Microsoft Docs"
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
  - "vbc30135"
  - "bc30135"
helpviewer_keywords: 
  - "BC30135"
ms.assetid: 099771a1-5bf4-4c16-8fc3-262926c771df
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;SyncLock&quot; 语句在即时窗口中无效
`SyncLock` 语句会同步线程，不允许用于调试上下文中。  
  
 **错误 ID：**BC30135  
  
### 更正此错误  
  
-   不要在“即时”窗口中发出 `SyncLock` 语句。  
  
## 请参阅  
 [即时窗口](../ide/reference/immediate-window.md)   
 [SyncLock 语句](/dotnet/visual-basic/language-reference/statements/synclock-statement)