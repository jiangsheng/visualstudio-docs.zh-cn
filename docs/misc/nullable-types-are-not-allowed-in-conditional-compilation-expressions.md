---
title: "条件编译表达式中不允许出现可以为 null 的类型 | Microsoft Docs"
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
  - "bc33111"
  - "vbc33111"
helpviewer_keywords: 
  - "BC33111"
ms.assetid: 2c2587e5-2179-4a31-bcf7-7004db6f2d73
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 条件编译表达式中不允许出现可以为 null 的类型
不能在条件编译指令的表达式中使用可以为 null 的类型。 例如，下面的代码会导致此错误。  
  
```vb#  
'#Const triggerPoint = 0 '' Not valid. '#If CType(triggerpoint, Boolean?) = True Then '        ' Body of the conditional directive. '#End If  
```  
  
 **错误 ID：**BC33111  
  
### 更正此错误  
  
-   删除可以为 null 的类型名称。  
  
## 请参阅  
 [可以为 Null 的值类型](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)   
 [\#If...Then...\#Else 指令](/dotnet/visual-basic/language-reference/directives/if-then-else-directives)   
 [条件编译](/dotnet/visual-basic/programming-guide/program-structure/conditional-compilation)