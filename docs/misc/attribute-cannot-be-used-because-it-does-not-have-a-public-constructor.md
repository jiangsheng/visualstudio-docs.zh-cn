---
title: "属性没有 Public 构造函数，因此不能使用。 | Microsoft Docs"
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
  - "vbc30758"
  - "bc30758"
helpviewer_keywords: 
  - "BC30758"
ms.assetid: b72d1ff2-f6b2-4a89-9ac2-8765f77bcc97
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 属性没有 Public 构造函数，因此不能使用。
正在使用的属性的构造函数是 `Private`，且无法使用。  
  
 **错误 ID：**BC30758  
  
### 更正此错误  
  
1.  如果看到你开发的自定义属性出现此错误，请将其 `Sub``New` 构造函数的访问修饰符更改为 `Public`。  
  
## 请参阅  
 [不在生成中：Visual Basic 中的属性](http://msdn.microsoft.com/zh-cn/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [对象生存期：如何创建和销毁对象](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)