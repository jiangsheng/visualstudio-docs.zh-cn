---
title: "约束“&lt;constraint1&gt;”与已为类型参数“&lt;typeparametername&gt;”指定的约束“&lt;constraint2&gt;”冲突。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32119"
  - "bc32119"
helpviewer_keywords: 
  - "BC32119"
ms.assetid: 30e6778d-5c2b-4f2d-a136-4e66fa9fbe4d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 约束“&lt;constraint1&gt;”与已为类型参数“&lt;typeparametername&gt;”指定的约束“&lt;constraint2&gt;”冲突。
使用类型参数上的冲突约束声明了一个泛型类型。  
  
 以下语句可能会生成此错误。  
  
 `Public Class testClass(Of t As {Structure, Class })`  
  
 约束 `Structure` 和 `Class` 导致类型参数 `t` 冲突，原因是 `Structure` 约束要求相应的类型变量为值类型，而 `Class` 要求类型变量为引用类型。  
  
 **错误 ID：**BC32119  
  
### 更正此错误  
  
-   更改类型参数约束以避免冲突。  
  
## 请参阅  
 [Visual Basic 中的泛型类型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [类型列表](/dotnet/visual-basic/language-reference/statements/type-list)   
 [结构 \(Visual Basic\)](http://msdn.microsoft.com/zh-cn/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [类 \(Visual Basic\)](http://msdn.microsoft.com/zh-cn/0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [值类型和引用类型](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)