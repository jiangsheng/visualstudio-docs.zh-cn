---
title: "“Set”参数的类型必须与包含属性的类型相同 | Microsoft Docs"
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
  - "vbc31064"
  - "bc31064"
helpviewer_keywords: 
  - "BC31064"
ms.assetid: f0b8310d-68a1-4989-ac64-03b1861528ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Set”参数的类型必须与包含属性的类型相同
`Set` 属性过程的参数的类型不同于其所属属性的类型。  
  
 **错误 ID：**BC31064  
  
### 更正此错误  
  
-   将参数的数据类型更改为 `Set`，使其匹配于属性的数据类型。 例如:  
  
    ```  
    Class Class1 ' Declare a local variable to hold the property value. Private Fval As Integer Property F() As Integer Get Return Fval End Get Set(ByVal Value As Integer) Fval = Value End Set End Property End Class  
    ```  
  
## 请参阅  
 [不在生成中：如何：将字段和属性添加到类](http://msdn.microsoft.com/zh-cn/ae53f61b-3abc-413e-8931-703c5f5e8fc2)   
 [Property 过程](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [不在生成中：属性和属性过程](http://msdn.microsoft.com/zh-cn/23e2a1ec-7e9d-4109-8940-c703d981077b)