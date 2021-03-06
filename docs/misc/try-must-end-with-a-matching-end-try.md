---
title: "“Try”必须以匹配的“End Try”结束 | Microsoft Docs"
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
  - "bc30384"
  - "vbc30384"
helpviewer_keywords: 
  - "BC30384"
ms.assetid: 898300b4-c091-4105-aeb0-9bd559ff6b6f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Try”必须以匹配的“End Try”结束
`Try` 用于启动 `Try` 块；因此它只能出现在块的开头，并以匹配的`End Try` 语句结束块。 存在冗余 `Try`，或未以 `Finally` 结束 `Try` 块。  
  
 **错误 ID：**BC30384  
  
### 更正此错误  
  
1.  查找并删除无关的 `Try`，或以匹配的 `End Try` 结束块。  
  
## 请参阅  
 [Try...Catch...Finally 语句](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic 的结构化异常处理概述](http://msdn.microsoft.com/zh-cn/bb81af80-a735-4873-9711-6151a48e418a)