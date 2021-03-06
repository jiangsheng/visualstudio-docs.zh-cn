---
title: "无法在对象初始值设定项表达式中初始化成员“&lt;membername&gt;”，原因是该成员已共享 | Microsoft Docs"
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
  - "bc30991"
  - "vbc30991"
helpviewer_keywords: 
  - "BC30991"
ms.assetid: 47e832b4-47e3-426e-b88c-5d5568102fde
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法在对象初始值设定项表达式中初始化成员“&lt;membername&gt;”，原因是该成员已共享
不能使用对象初始值设定项来初始化声明为共享的类的任何成员。 有关详细信息，请参阅[Shared](/dotnet/visual-basic/language-reference/modifiers/shared)。  
  
 **错误 ID：**BC30991  
  
### 更正此错误  
  
1.  检查类定义以确定共享了哪个成员。  
  
2.  消除了对象初始值设定项列表中该成员的初始化。  
  
## 示例  
 在下面的示例中，`totalCustomers` 是一个共享成员。  
  
```  
Public Class Customer Public Shared totalCustomers As Integer ' Other declarations and method definitions. End Class  
```  
  
 由于 `totalCustomers` 是共享成员，因此尝试在对象初始值设定项列表中设置其初始值导致了此错误。  
  
```  
' This declaration is not valid. ' Dim cust As New Customer With { .Name = "Coho Winery", _ '                                 .totalCustomers = 21 }  
```  
  
## 请参阅  
 [对象初始值设定项：命名类型和匿名类型](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)   
 [不在生成中：Visual Basic 中的共享成员](http://msdn.microsoft.com/zh-cn/dbc3783f-83a2-4225-995d-c2d6d025663d)