---
title: "“WithEvents”变量只能类型化为具有类约束的类、接口或类型参数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30413"
  - "bc30413"
helpviewer_keywords: 
  - "BC30413"
ms.assetid: 11ddf207-2760-425f-b4c2-bb9fe6da36ea
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “WithEvents”变量只能类型化为具有类约束的类、接口或类型参数
声明了类型化为与 `WithEvents` 一起使用的结构的变量，这不是 `WithEvents` 修饰符的有效使用。  
  
 **错误 ID：**BC30413  
  
### 更正此错误  
  
1.  使用 `AddHandler` 来处理结构中定义的事件。  
  
## 请参阅  
 [不在生成中：WithEvents 和 Handles 子句](http://msdn.microsoft.com/zh-cn/072b9cf6-6298-46f1-849e-4edc1631564c)   
 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [AddHandler 语句](/dotnet/visual-basic/language-reference/statements/addhandler-statement)