---
title: "编译器错误 CS0180 | Microsoft Docs"
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
  - "CS0180"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0180"
ms.assetid: a21bf0a2-ed5a-4ddd-88d3-240babc5888a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0180
“member”不能既是外部的又是抽象的  
  
 [abstract](/dotnet/csharp/language-reference/keywords/abstract) 和 [extern](/dotnet/csharp/language-reference/keywords/extern) 关键字互相排斥。`extern` 关键字表示在文件外部定义成员，**abstract** 意味着在派生类中提供了该实现。 有关更多信息，请参见[方法](/dotnet/csharp/programming-guide/classes-and-structs/methods)。  
  
 以下示例生成 CS0180：  
  
```  
// CS0180.cs namespace MyNamespace { public class MyClass { public extern abstract int Foo(int a);   // CS0180 public static void Main() { } } }  
```