---
title: "Option Strict On 要求所有变量声明都包含“As”子句 | Microsoft Docs"
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
  - "bc30209"
  - "vbc30209"
helpviewer_keywords: 
  - "BC30209"
ms.assetid: 69c2e32a-86aa-4075-a142-440605a7063a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On 要求所有变量声明都包含“As”子句
声明中包含没有 `As` 子句的已声明变量。 当 `Option Strict` 为 `On` 时，必须用 `As` 子句来声明每个变量、属性、过程参数和函数返回，以指定其数据类型；例如 `Dim MyNum As Short`。  
  
 **错误 ID：**BC30209  
  
### 更正此错误  
  
1.  检查 `As` 关键字是否拼写错误。  
  
2.  为已声明的变量提供 `As` 子句，或关闭 `Option Strict Off`。  
  
## 请参阅  
 [Option Strict 语句](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [变量声明](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)