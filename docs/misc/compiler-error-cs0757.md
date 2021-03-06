---
title: "编译器错误 CS0757 | Microsoft Docs"
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
  - "CS0757"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0757"
ms.assetid: ba093570-306d-4b7b-aad5-1a3855ad6776
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0757
分部方法不能有多个实现声明。  
  
 分部方法必须包含一个（且仅限一个）定义声明（签名），并可包含一个或零个实现声明（主体）。 同一定义声明不允许有多个实现声明。 可以重载分部方法，并且每个重载版本都可以有一个或零个实现方法。  
  
### 更正此错误  
  
1.  从分部方法中删除所有多余的实现声明，只保留一个实现声明。  
  
## 示例  
 下面的示例生成 CS0757：  
  
```  
// cs0757.cs using System; public partial class C { // Defining declaration. partial void Part(); // Implementing declaration. partial void Part() { //...Do something. } // Second implementing declaration. partial void Part() // CS0757 { //...Do something. } public static int Main() { return 1; } }  
```  
  
## 请参阅  
 [分部类和方法](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)