---
title: "“&lt;specifier&gt;”在接口事件声明中无效 | Microsoft Docs"
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
  - "bc30275"
  - "vbc30275"
helpviewer_keywords: 
  - "BC30275"
ms.assetid: bd12c952-c619-4753-8d6d-90ef4086fdc2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;specifier&gt;”在接口事件声明中无效
接口内的 `Event` 语句包含不允许的关键字，如 `Implements`。 接口只能定义成员，而不能实现它们。  
  
 **错误 ID：**BC30275  
  
### 更正此错误  
  
1.  从声明语句中删除关键字。  
  
2.  将接口成员的实现移动到实现该接口的类。  
  
## 请参阅  
 [Interface 语句](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Implements 语句](/dotnet/visual-basic/language-reference/statements/implements-statement)