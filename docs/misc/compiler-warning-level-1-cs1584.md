---
title: "编译器警告（等级 1）CS1584 | Microsoft Docs"
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
  - "CS1584"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1584"
ms.assetid: 56c8f9bf-4cce-4269-b573-d60e5b11f9ab
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器警告（等级 1）CS1584
“member”的 XML 注释中出现语法错误的 cref 特性“invalid\_syntax”  
  
 传递给文档注释标记的其中一个参数的语法无效。 有关详细信息，请参阅[建议的文档注释标记](/dotnet/csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments)。  
  
## 示例  
 下面的示例生成 CS1584。  
  
```  
// CS1584.cs // compile with: /W:1 /doc:CS1584.xml /// <remarks>Test class</remarks> public class Test { /// <remarks>Called in <see cref="Test.Mai()n"/>.</remarks>   // CS1584 // try the following line instead // /// <remarks>Called in <see cref="Test.Main()"/>.</remarks> public static void Test2() {} /// <remarks>Main method</remarks> public static void Main() {} }  
```