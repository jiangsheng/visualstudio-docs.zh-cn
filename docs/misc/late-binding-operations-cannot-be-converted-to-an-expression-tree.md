---
title: "无法将后期绑定运算转换为表达式树 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36604"
  - "bc36604"
helpviewer_keywords: 
  - "BC36604"
ms.assetid: 6fd66d12-8c99-46e0-9095-fe1b29fd2692
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法将后期绑定运算转换为表达式树
试图将后期绑定操作转换为表达式树。 这是无效的。 例如，下面的代码会导致此错误。  
  
```vb#  
Option Strict Off Module Module1 Sub Main() '' Not valid. ' Test(Function(someInstance) someInstance.SomeProperty) End Sub Sub Test(ByVal ex As Expressions.Expression(Of Func(Of Object, Object))) End Sub End Module  
```  
  
 **错误 ID：**BC36604  
  
## 请参阅  
 [早期绑定和后期绑定](/dotnet/visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding)   
 [不在生成中：LINQ 中的表达式树](http://msdn.microsoft.com/zh-cn/1a2e8e74-4bbc-45ab-9a46-2b6cfce3bcb2)