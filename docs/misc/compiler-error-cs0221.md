---
title: "编译器错误 CS0221 | Microsoft Docs"
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
  - "CS0221"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0221"
ms.assetid: 97170b49-54f1-4dac-a865-2f9cc6bf55b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0221
常量值“value”无法转换为“type”\(使用“unchecked”语法重写\)  
  
 [checked](/dotnet/csharp/language-reference/keywords/checked)（默认情况下处于打开状态）检测到会导致数据丢失的赋值操作。 更正赋值或使用 [unchecked](/dotnet/csharp/language-reference/keywords/unchecked) 解决此错误。 有关详细信息，请参阅[Checked 和 Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)。  
  
 下面的示例生成 CS0221：  
  
```  
// CS0221.cs public class MyClass { public static void Main() { // unchecked // { int a = (int)0xFFFFFFFF;   // CS0221 a++; // } } }  
```