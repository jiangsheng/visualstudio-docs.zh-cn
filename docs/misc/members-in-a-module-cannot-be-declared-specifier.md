---
title: "模块中的成员不能声明为“&lt;specifier&gt;” | Microsoft Docs"
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
  - "vbc30436"
  - "bc30436"
helpviewer_keywords: 
  - "BC30436"
ms.assetid: c0560864-64f6-4c76-803f-d9c51df89d62
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 模块中的成员不能声明为“&lt;specifier&gt;”
你使用了在 `Module` 语句内的成员上无效的说明符。 模块永远不能实例化，不支持继承且不能实现接口。  
  
 **错误 ID：**BC30436  
  
### 更正此错误  
  
-   删除说明符。  
  
## 请参阅  
 [Module 语句](/dotnet/visual-basic/language-reference/statements/module-statement)