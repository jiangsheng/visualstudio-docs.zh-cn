---
title: "应为“Assembly”或“Module” | Microsoft Docs"
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
  - "vbc32015"
  - "bc32015"
helpviewer_keywords: 
  - "BC32015"
ms.assetid: 6e62fe8d-a875-4995-b6b2-443e75c65e85
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 应为“Assembly”或“Module”
在未指示某个全局特性是应用于整个程序集还是仅应用于当前模块的情况下指定了该特性。 全局特性必须指定 `Assembly` 或 `Module`。  
  
 全局特性是单独出现在源行上的特性，而不是应用于特定编程元素的声明。  
  
 **错误 ID：**BC32015  
  
### 更正此错误  
  
1.  如果希望特性是全局特性，请将 `Assembly` 或 `Module` 关键字添加到特性块的开头，后跟一个冒号 \(:\)。  
  
2.  如果不希望特性是全局特性，请删除特性块，或将它移动到编程元素声明。  
  
## 请参阅  
 [Assembly](/dotnet/visual-basic/language-reference/modifiers/assembly)   
 [Module \<keyword\>](../Topic/Module%20%3Ckeyword%3E%20\(Visual%20Basic\).md)   
 [不在生成中：特性的应用程序](http://msdn.microsoft.com/zh-cn/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [不在生成中：Visual Basic 中的全局特性](http://msdn.microsoft.com/zh-cn/253a32d8-1531-4504-b687-088554ab71d2)