---
title: "“System.Runtime.InteropServices.DllImportAttribute”不能应用于带有非空体的 Sub、Function 或 Operator | Microsoft Docs"
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
  - "bc31522"
  - "vbc31522"
helpviewer_keywords: 
  - "BC31522"
ms.assetid: 9548cf98-8a13-4f09-b6b5-2f57273c1571
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “System.Runtime.InteropServices.DllImportAttribute”不能应用于带有非空体的 Sub、Function 或 Operator
向 `Sub`、`Function` 或不为空的 `Operator` 应用了 `DllImportAttribute` 特性。  
  
 **错误 ID：**BC31522  
  
### 更正此错误  
  
-   从 `Sub`、`Function` 或 `Operator` 删除所有代码以使用此特性。  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Declare 语句](/dotnet/visual-basic/language-reference/statements/declare-statement)