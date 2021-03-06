---
title: "“Finally”不能出现在“Try”语句之外 | Microsoft Docs"
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
  - "vbc30382"
  - "bc30382"
helpviewer_keywords: 
  - "BC30382"
ms.assetid: 0314d8d2-18bc-4bbd-858c-0a18408b52fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Finally”不能出现在“Try”语句之外
`Finally` 用于完成 `Try...Catch...Finally` 块；因此它只能在块的末尾出现一次。 或者有不必要的 `Finally`，或者 `Finally` 语句出现在其对应 `Try` 块的边界之外。  
  
 **错误 ID:** BC30382  
  
### 更正此错误  
  
1.  找到并删除不必要的 `Finally` 语句。  
  
2.  将 `Finally` 语句移到代码中的适当位置。  
  
## 请参阅  
 [Try...Catch...Finally 语句](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic 的结构化异常处理概述](http://msdn.microsoft.com/zh-cn/bb81af80-a735-4873-9711-6151a48e418a)