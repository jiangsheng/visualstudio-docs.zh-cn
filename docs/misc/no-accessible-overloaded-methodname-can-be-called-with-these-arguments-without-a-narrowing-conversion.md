---
title: "必须进行收缩转换才能用这些参数调用可访问的重载“&lt;methodname&gt;” | Microsoft Docs"
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
  - "vbrAmbiguousMatch_NarrowingConversion1"
ms.assetid: 2fdbadb9-8ef1-404a-a2ed-ce5f5e55cfcb
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 必须进行收缩转换才能用这些参数调用可访问的重载“&lt;methodname&gt;”
调用了重载方法，但是方法不可与所提供的未进行收缩转换的参数列表相匹配。  
  
### 更正此错误  
  
1.  指定 `Option Strict Off`。  
  
2.  更改参数以匹配重载方法的其中一个签名。  
  
## 请参阅  
 [通过值和通过引用传递参数](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)   
 [扩大转换和收缩转换](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)