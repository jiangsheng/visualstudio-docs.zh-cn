---
title: "“&lt;parametername&gt;”已被声明为此方法的类型参数 | Microsoft Docs"
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
  - "bc32089"
  - "vbc32089"
helpviewer_keywords: 
  - "BC32089"
ms.assetid: 5e440b4b-f62b-4ff5-9148-2372d4752bf6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “&lt;parametername&gt;”已被声明为此方法的类型参数
泛型过程使用与类型参数相同的名称定义普通参数或局部变量。  
  
 过程的每个参数（包括泛型过程的每个类型参数）必须具有与所有其他参数不同的名称。 由于过程参数被用作局部变量，因此在过程中声明的任何局部变量也必须具有与所有参数和类型参数不同的名称。  
  
 **错误 ID：**BC32089  
  
### 更正此错误  
  
-   更改普通参数或本地变量的名称。  
  
## 请参阅  
 [Visual Basic 中的泛型过程](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [参数列表](/dotnet/visual-basic/language-reference/statements/parameter-list)