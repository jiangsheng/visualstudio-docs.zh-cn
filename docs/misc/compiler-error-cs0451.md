---
title: "编译器错误 CS0451 | Microsoft Docs"
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
  - "CS0451"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0451"
ms.assetid: e73544f8-856b-4a92-90e0-dd6cb9d688b1
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0451
"new\(\)" 约束不能与 "struct" 约束一起使用  
  
 当指定泛型类型上的约束时，`new()` 约束只可与类类型约束、接口类型约束、引用类型约束和类型形参约束一起使用，不可与值类型约束一起使用。  
  
## 示例  
 下面的示例生成 CS0451。  
  
```  
// CS0451.cs using System; public class C4 { public void F4<T>() where T : struct, new() {}   // CS0451 } // OK public class C5 { public void F5<T>() where T : struct {} } public class C6 { public void F6<T>() where T : new() {} }  
  
```