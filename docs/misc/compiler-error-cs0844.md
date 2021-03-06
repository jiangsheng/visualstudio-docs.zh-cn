---
title: "编译器错误 CS0844 | Microsoft Docs"
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
  - "CS0844"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0844"
ms.assetid: ccf74e01-292a-42d0-897c-8add7aee2118
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0844
局部变量“name”在声明之前无法使用。 局部变量的声明隐藏字段“name”。  
  
 标识符在给定块中只能有一种含义。 通过为该标识符引入另一种含义，与类字段同名的局部变量可以隐藏字段。 因此，如果在方法中引用类字段，然后使用相同名称声明局部变量，则编译器将生成错误。  
  
### 更正此错误  
  
-   使用 `this.num` 引用类字段。  
  
-   为局部变量提供一个与类字段名称不同的名称。  
  
## 示例  
 下面的代码生成 CS0844：  
  
```  
class Test { int num; public void TestMethod() { num = 5; // CS0844 int num = 6;        } public static int Main() { return 1; } }  
```