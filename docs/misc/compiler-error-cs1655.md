---
title: "编译器错误 CS1655 | Microsoft Docs"
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
  - "CS1655"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1655"
ms.assetid: 041e9daa-c026-494f-b086-0db9a23c969b
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1655
不能将“变量”字段作为 ref 或 out 参数传递，因为它是“只读变量类型”  
  
 如果尝试将 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 变量、[using](/dotnet/csharp/language-reference/keywords/using-statement) 变量或 [fixed](/dotnet/csharp/language-reference/keywords/fixed-statement) 变量的成员作为 ref 或 out 参数传递给函数，会发生此错误。 由于在这种上下文中，这些变量被视为只读，因此不允许这样做。  
  
 下面的示例生成 CS1655:  
  
```  
// CS1655.cs struct S { public int i; } class CMain { static void f(ref int iref) { } public static void Main() { S[] sa = new S[10]; foreach(S s in sa) { CMain.f(ref s.i);  // CS1655 } } }  
```