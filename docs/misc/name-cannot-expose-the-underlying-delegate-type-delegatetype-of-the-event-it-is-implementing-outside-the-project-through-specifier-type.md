---
title: "“&lt;名称&gt;”不能公开事件的基础委托类型“&lt;委托类型&gt;”，它正通过&lt;标识符&gt;“&lt;类型&gt;”在项目外部实现 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30915"
  - "vbc30915"
helpviewer_keywords: 
  - "BC30915"
ms.assetid: 9e6cc2bf-1d06-4034-9334-93ef076474c0
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;名称&gt;”不能公开事件的基础委托类型“&lt;委托类型&gt;”，它正通过&lt;标识符&gt;“&lt;类型&gt;”在项目外部实现
该代码在公共类外部公开了一个私有类型。  
  
 **错误 ID：**BC30915  
  
### 更正此错误  
  
-   将该类型声明为 `Public`。  
  
     \- 或 \-  
  
-   使用另一种类型。  
  
## 请参阅  
 [不在生成中：Visual Basic 中的面向对象编程](http://msdn.microsoft.com/zh-cn/691365cf-9547-4a8f-aaca-36aaf1e8911a)