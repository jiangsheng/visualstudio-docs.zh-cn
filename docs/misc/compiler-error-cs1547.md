---
title: "编译器错误 CS1547 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1547"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1547"
ms.assetid: 40029557-076a-47d8-aabc-d86c56a846d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1547
关键字 "void" 不能在此上下文中使用  
  
 编译器检测到无效的 [void](/dotnet/csharp/language-reference/keywords/void) 关键字使用。  
  
 下面的示例生成 CS1547：  
  
```  
// CS1547.cs public class MyClass { void BadMethod() { void i;   // CS1547, cannot have variables of type void } public static void Main() { } }  
```