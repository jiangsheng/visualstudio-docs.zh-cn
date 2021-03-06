---
title: "编译器错误 CS1661 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1661"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1661"
ms.assetid: 162d5736-ca3c-4a09-a5d9-a19da3d5bf24
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS1661
不能将匿名方法块转换为委托类型“delegate type”，因为指定块的参数类型与委托参数类型不匹配  
  
 如果在匿名方法定义中，匿名方法的参数类型不匹配委托参数类型，会发生此错误。 检查参数数目、参数类型和所有 ref 或 out 参数并验证是否完全匹配。  
  
 以下示例生成 CS1661：  
  
```  
// CS1661.cs delegate void MyDelegate(int i); class C { public static void Main() { MyDelegate d = delegate(string s) { };  // CS1661 } }  
```