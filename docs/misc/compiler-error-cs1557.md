---
title: "编译器错误 CS1557 | Microsoft Docs"
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
  - "CS1557"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1557"
ms.assetid: 1615e028-aeb7-4788-bd87-8e49e502d698
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1557
无法对 Main 方法使用“class”，因为它在不同的输出文件中  
  
 为一个多输出文件编译中的输出文件指定了 [\/main](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) 编译器选项。 但是，在 \/main 编译的源代码中未找到该类；在编译内的一个其他输出文件的源代码文件中找到了该类。