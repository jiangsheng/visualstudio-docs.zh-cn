---
title: "命名空间声明必须以“xmlns”开头 | Microsoft Docs"
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
  - "bc31187"
  - "vbc31187"
helpviewer_keywords: 
  - "BC31187"
ms.assetid: 64c6a033-7cdc-48a0-bff0-bdd045cb13ad
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 命名空间声明必须以“xmlns”开头
已指定的 XML 命名空间没有需要的 `xmlns` 标识符。`xmlns` 标识符必须仅包含小写字符。  
  
 **错误 ID：**BC31187  
  
### 更正此错误  
  
-   声明 XML 命名空间时使用 `xmlns` 标识符。 下面是一个示例：  
  
    ```vb#  
    Imports <xmlns:ns="http://SampleNamespace">  
    ```  
  
## 请参阅  
 [Imports 语句（XML 命名空间）](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)   
 [XML 文本](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)