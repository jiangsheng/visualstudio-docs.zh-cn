---
title: "编译器错误 CS0082 | Microsoft Docs"
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
  - "CS0082"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0082"
ms.assetid: 7612976f-de2c-4f6b-87c9-43175821650c
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器错误 CS0082
类型“type”已保留了一个名为“name”的具有相同参数类型的成员  
  
 属性在编译时被转换为标识符前带有 `get_` 和\/或 `set_` 的方法。 如果定义自己的方法，且该方法与方法名称冲突，将生成错误。  
  
## 示例  
 下面的示例生成 CS0082：  
  
```  
//cs0082.cs class MyClass { //property public int MyProp { get //CS0082 { return 1; } } //conflicting Get public int get_MyProp() { return 2; } public static int Main() { return 1; } }  
```  
  
## 请参阅  
 [属性](/dotnet/csharp/programming-guide/classes-and-structs/properties)