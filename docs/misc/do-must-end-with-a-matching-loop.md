---
title: "“Do”必须以匹配的“Loop”结束 | Microsoft Docs"
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
  - "vbc30083"
  - "bc30083"
helpviewer_keywords: 
  - "BC30083"
ms.assetid: b157b9e3-57fa-4324-a13d-b37bcf0861e6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Do”必须以匹配的“Loop”结束
出现 `Do` 语句而没有相应的 `Loop` 语句。 必须使用 `Loop` 语句结束 `Do` 循环。  
  
 **错误 ID：**BC30083  
  
### 更正此错误  
  
-   如果此 `Do` 循环是一组嵌套循环的一部分，请确保每个循环正常终止。  
  
-   将 `Loop` 语句添加到 `Do` 循环末尾。  
  
## 请参阅  
 [Do...Loop 语句](/dotnet/visual-basic/language-reference/statements/do-loop-statement)