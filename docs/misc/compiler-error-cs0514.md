---
title: "编译器错误 CS0514 | Microsoft Docs"
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
  - "CS0514"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0514"
ms.assetid: 74ce3010-f9e9-458c-8b68-cfb908a3e7a2
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0514
“constructor”：静态构造函数不能具有显式的“this”或“base”构造函数调用  
  
 不允许在静态构造函数中调用 `this`，因为将在创建类的任何实例之前自动调用静态构造函数。 同时不会继承静态构造函数，且不能直接对其进行调用。  
  
 有关详细信息，请参阅[this](/dotnet/csharp/language-reference/keywords/this)和[base](/dotnet/csharp/language-reference/keywords/base)。  
  
## 示例  
 下面的示例生成 CS0514：  
  
```  
// CS0514.cs class A { static A() : base(0) // CS0514 { } public A(object o) { } } class B { static B() : this(null) // CS0514 { } public B(object o) { } }  
```