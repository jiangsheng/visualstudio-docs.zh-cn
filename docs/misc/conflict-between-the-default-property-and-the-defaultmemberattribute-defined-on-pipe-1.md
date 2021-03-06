---
title: "默认属性与“|1”上定义的“DefaultMemberAttribute”之间有冲突。 | Microsoft Docs"
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
  - "vbc32304"
  - "bc32304"
helpviewer_keywords: 
  - "BC32304"
ms.assetid: 42803d13-ff1d-40ed-a4a8-269e2fb4aa01
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 默认属性与“|1”上定义的“DefaultMemberAttribute”之间有冲突。
类、结构或接口用 [Default](/dotnet/visual-basic/language-reference/modifiers/default) 关键字声明了默认属性，又应用 <xref:System.Reflection.DefaultMemberAttribute> 将另一个成员指定为默认成员。  
  
 一个类型最多可以有一个默认成员。 在声明默认属性时，Visual Basic 会自动将 <xref:System.Reflection.DefaultMemberAttribute> 应用到指定该属性的类、结构或接口。  
  
 **错误 ID：**BC32304  
  
### 更正此错误  
  
1.  决定哪个成员应是该类、结构或接口的默认成员。  
  
2.  删除冲突的声明（`Default` 关键字或 <xref:System.Reflection.DefaultMemberAttribute>）。  
  
## 请参阅  
 <xref:System.Reflection.DefaultMemberAttribute>   
 [Default](/dotnet/visual-basic/language-reference/modifiers/default)   
 [不在生成中：默认属性](http://msdn.microsoft.com/zh-cn/a70f2a27-8176-4858-935e-f25afdd43ab5)   
 [如何：在 Visual Basic 中声明和调用默认属性](../Topic/How%20to:%20Declare%20and%20Call%20a%20Default%20Property%20in%20Visual%20Basic.md)