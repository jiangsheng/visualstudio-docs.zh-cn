---
title: "编译器警告（等级 3）CS0105 | Microsoft Docs"
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
  - "CS0105"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0105"
ms.assetid: 96d1d5d7-79e9-424f-bbde-f87e88b70003
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器警告（等级 3）CS0105
“namespace”的 using 指令以前在此命名空间中出现过  
  
 一个只应声明一次的[命名空间](/dotnet/csharp/language-reference/keywords/namespace)声明了多次；删除所有重复的命名空间声明。  
  
 下面的示例生成 CS0105：  
  
```  
// CS0105.cs // compile with: /W:3 using System; using System;   // CS0105 public class a { public static void Main() { } }  
```