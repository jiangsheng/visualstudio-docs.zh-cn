---
title: "此“Sub New”的第一条语句必须是对“MyBase.New”或“MyClass.New”的显式调用，原因是“&lt;derivedclassname&gt;”的基类“&lt;baseclassname&gt;”中“&lt;constructorname&gt;”被标为已过时。 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30919"
  - "bc30919"
helpviewer_keywords: 
  - "BC30919"
ms.assetid: 437e3204-8ddc-45d3-b9b4-c66d53a61a6d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 此“Sub New”的第一条语句必须是对“MyBase.New”或“MyClass.New”的显式调用，原因是“&lt;derivedclassname&gt;”的基类“&lt;baseclassname&gt;”中“&lt;constructorname&gt;”被标为已过时。
类构造函数不显式调用基类构造函数，并且隐式基类构造函数标有 <xref:System.ObsoleteAttribute> 特性和将其视为错误的指令。  
  
 当派生的类构造函数不调用基类构造函数时，[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 会尝试生成对无参数基类构造函数的隐式调用。 如果基类中没有无需参数即可调用的构造函数，则 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 无法生成隐式调用。 在这种情况下，所需的构造函数标记有 <xref:System.ObsoleteAttribute> 特性，因此 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 不能调用它。  
  
 可以通过将 <xref:System.ObsoleteAttribute> 应用于任意编程元素，将其标记为不再使用。 如果执行此操作，则可以将特性的 <xref:System.ObsoleteAttribute.IsError%2A> 属性设置为 `True` 或 `False`。 如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。 如果设置为 `False`，或将其默认为 `False`，则编译器会在有操作尝试使用该元素时发出警告。  
  
 **错误 ID：**BC30919  
  
### 更正此错误  
  
-   将对 `MyBase.New()` 或 `MyClass.New()` 的调用包括为派生类中 `Sub New` 的第一个语句。  
  
## 请参阅  
 [不在生成中：Visual Basic 中使用的特性](http://msdn.microsoft.com/zh-cn/22231318-8a40-49af-9245-e0aab723563b)   
 [不在生成中：特性的应用程序](http://msdn.microsoft.com/zh-cn/2b1703ed-4437-49b3-bc0b-568094324f47)