---
title: "“&lt;method&gt;”是“&lt;modifier&gt;”，因此它在此上下文中不可访问。 | Microsoft Docs"
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
  - "vbc30389"
  - "bc30389"
helpviewer_keywords: 
  - "BC30389"
ms.assetid: fae58a68-df91-4741-a8c9-f1bb10e166e2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;method&gt;”是“&lt;modifier&gt;”，因此它在此上下文中不可访问。
试图访问一个由于被声明为 `Private` 而在此上下文中不可访问的方法。 出现此错误的原因可能是 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 编译器导入类的所有成员，并且不区分大小写，因此仅通过大小写区分的名称可能发生冲突。  
  
 **错误 ID：**BC30389  
  
### 更正此错误  
  
-   请考虑将方法声明为 `Public`。  
  
-   如果错误由名称冲突引起的，则不仅仅通过大小写来区分冲突的名称。  
  
## 请参阅  
 [Private](/dotnet/visual-basic/language-reference/modifiers/private)