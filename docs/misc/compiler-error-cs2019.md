---
title: "编译器错误 CS2019 | Microsoft Docs"
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
  - "CS2019"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2019"
ms.assetid: eafd2531-8b3a-499c-9e12-a605a011396f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS2019
\/target 的目标类型无效: 必须指定“exe”、“winexe”、“library”或“module”  
  
 [\/target](/dotnet/csharp/language-reference/compiler-options/target-compiler-option) 编译器选项已使用，但传递的是无效参数。 若要解决此错误，请使用适合输出文件的 **\/target** 选项的形式重新编译程序。  
  
 以下示例生成 CS2017：  
  
```  
// CS2019.cs // compile with: /target:libra // CS2019 expected class MyClass { }  
```