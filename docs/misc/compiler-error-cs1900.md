---
title: "编译器错误 CS1900 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1900"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1900"
ms.assetid: 08141138-bfea-4af3-a9a0-ec54cf2caa13
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1900
警告等级必须在 0\-4 的范围内  
  
 [\/warn](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option) 编译器选项只能带五个可能的值（0、1、2、3 或 4）之一。 传递给 **\/warn** 的其他任何值均将导致 CS1900。  
  
 下面的示例生成 CS1900：  
  
```  
// CS1900.cs // compile with: /W:5 // CS1900 expected class x { public static void Main() { } }  
```