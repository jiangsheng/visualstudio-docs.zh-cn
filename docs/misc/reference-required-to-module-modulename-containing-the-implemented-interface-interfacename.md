---
title: "需要对模块“&lt;modulename&gt;”（包含已实现的接口“&lt;interfacename&gt;”）的引用 | Microsoft Docs"
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
  - "vbc30010"
  - "bc30010"
helpviewer_keywords: 
  - "BC30010"
ms.assetid: 57fe7e15-bf99-49d1-ba6c-bb7abeb615b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 需要对模块“&lt;modulename&gt;”（包含已实现的接口“&lt;interfacename&gt;”）的引用
需要对模块“\<modulename\>”（包含已实现的接口“\<interfacename\>”）的引用。 请向项目中添加一个。  
  
 在你的项目中未直接引用的模块中定义接口。 如果接口是在多个模块中定义的，则 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 编译器需要引用以避免多义性。  
  
 **错误 ID：**BC30010  
  
### 更正此错误  
  
-   将未引用模块的名称包括在项目引用中。  
  
## 请参阅  
 [NIB：引用命名空间和组件](http://msdn.microsoft.com/zh-cn/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [有关无效的引用的疑难解答](../ide/troubleshooting-broken-references.md)