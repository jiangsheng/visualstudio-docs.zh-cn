---
title: "编译器错误 CS1542 | Microsoft Docs"
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
  - "CS1542"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1542"
ms.assetid: d7f60aa2-6645-472c-ac12-fa57a09fbd87
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1542
“dll”无法添加到此程序集中，因为它已经是程序集；请使用“\/R”选项  
  
 使用 [\/addmodule](/dotnet/csharp/language-reference/compiler-options/addmodule-compiler-option) 编译器选项引用的文件不是使用 [\/target:module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md) 生成的；在此编译中使用 [\/reference](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option) 来引用该文件。