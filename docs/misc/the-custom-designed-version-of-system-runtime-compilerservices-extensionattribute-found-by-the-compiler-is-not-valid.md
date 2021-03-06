---
title: "编译器找到的“System.Runtime.CompilerServices.ExtensionAttribute”自定义设计版本无效 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36558"
  - "bc36558"
helpviewer_keywords: 
  - "BC36558"
ms.assetid: f47d310a-95fd-4340-bda2-21262c217dbb
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 编译器找到的“System.Runtime.CompilerServices.ExtensionAttribute”自定义设计版本无效
编译器找到的“System.Runtime.CompilerServices.ExtensionAttribute”自定义设计版本无效。 其特性使用标志必须设置为允许程序集、类和方法。  
  
 编译器找到的 <xref:System.Runtime.CompilerServices.ExtensionAttribute?displayProperty=fullName> 的自定义设计的版本没有设置其特性使用标志，以向程序集、方法和类启用该特性的应用程序。 至少这三个程序元素的应用程序是必需的。  
  
 **错误 ID：**BC36558  
  
### 更正此错误  
  
-   更改特性定义，以至少使特性可应用于程序集、方法和类的特性，如下面的示例所示。  
  
-   使用 <xref:System.Runtime.CompilerServices.ExtensionAttribute?displayProperty=fullName> 而不是自定义设计版本。  
  
## 示例  
 下面的示例使用 `AttributeUsage` 特性来指定可向其应用 `ExtensionAttribute` 新版本的程序元素。 该示例指定 `AttributeTargets` 枚举的三个成员：`Assembly`、`Class` 和 `Method`。 省略这些元素中的任何一个都将导致此错误。  
  
```  
Namespace System.Runtime.CompilerServices <AttributeUsage(AttributeTargets.Assembly Or _ AttributeTargets.Class Or AttributeTargets.Method)> Class ExtensionAttribute Inherits System.Attribute ' Definitions of methods, fields, and properties. End Class End Namespace  
```  
  
 或者，你可以通过使用 `AttributeTargets` 的 `All`成员，允许 `ExtensionAttribute` 应用于所有程序元素。  
  
```  
<AttributeUsage(AttributeTargets.All)>  
```  
  
 删除 `AttributeUsage` 行（如下面的代码中所示）将产生相同的结果。  
  
```  
Namespace System.Runtime.CompilerServices Class ExtensionAttribute Inherits System.Attribute ' Definitions of methods, fields, and properties. End Class End Namespace  
```  
  
## 请参阅  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [不在生成中：Visual Basic 中的特性概述](http://msdn.microsoft.com/zh-cn/0d0cff64-892d-4f57-83bd-bef388553d4f)   
 [不在生成中：Visual Basic 中的自定义特性](http://msdn.microsoft.com/zh-cn/d72d8a5c-8f64-4614-b15b-cad66845d047)   
 [扩展方法](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [不在生成中：如何：定义你自己的特性](http://msdn.microsoft.com/zh-cn/039609c4-ec43-4f44-945f-aa3b5b535c6a)   
 [编写自定义特性](../Topic/Writing%20Custom%20Attributes.md)