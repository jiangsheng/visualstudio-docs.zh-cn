---
title: "编译器错误 CS0176 | Microsoft Docs"
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
  - "CS0176"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0176"
ms.assetid: 783c13d8-5ac3-4aeb-bd63-0468cb05550d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0176
不能使用实例引用访问静态成员“成员”，而是使用类型名称来限定它  
  
 仅可使用类名限定[静态](/dotnet/csharp/language-reference/keywords/static)变量；实例名称不能做为限定符。 有关详细信息，请参阅[静态类和静态类成员](/dotnet/csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members)。  
  
 下面的示例生成 CS0176：  
  
```  
// CS0176.cs public class MyClass2 { public static int num; } public class Test { public static void Main() { MyClass2 mc2 = new MyClass2(); int i = mc2.num;   // CS0176 // try the following line instead // int i = MyClass2.num; } }  
  
```