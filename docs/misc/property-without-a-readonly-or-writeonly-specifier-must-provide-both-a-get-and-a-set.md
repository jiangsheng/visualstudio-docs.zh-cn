---
title: "不带“ReadOnly”或“WriteOnly”说明符的属性必须同时提供“Get”和“Set” | Microsoft Docs"
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
  - "bc30124"
  - "vbc30124"
helpviewer_keywords: 
  - "BC30124"
ms.assetid: b24fc997-9a6b-44d1-b712-dab498a6fc72
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 不带“ReadOnly”或“WriteOnly”说明符的属性必须同时提供“Get”和“Set”
如果某个属性未声明为 `ReadOnly` 或 `WriteOnly`，则它必须提供用于读取和写入其值的过程。  
  
 **错误 ID：**BC30124  
  
### 更正此错误  
  
1.  请确保 `Property` 语句和 `End Property` 语句之间包含 `Get` 过程和 `Set` 过程。  
  
2.  验证 `Property` 声明中的其他过程是否正确终止。  
  
## 请参阅  
 [Property 语句](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get 语句](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [Set 语句](/dotnet/visual-basic/language-reference/statements/set-statement)