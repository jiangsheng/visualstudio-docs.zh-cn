---
title: "System.CLSCompliantAttribute 不能应用于属性“Get”/“Set”。 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40043"
  - "BC40043"
helpviewer_keywords: 
  - "BC40043"
ms.assetid: 2ff45c09-32be-4ca9-b42a-63ce2536db7d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# System.CLSCompliantAttribute 不能应用于属性“Get”/“Set”。
属性定义将 <xref:System.CLSCompliantAttribute> 特性应用于其 `Get` 或 `Set` 语句。  
  
 对于符合 [语言独立性和与语言无关的组件](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) 的属性，整个属性必须标记为 `<CLSCompliant(True)>`。 你必须将 <xref:System.CLSCompliantAttribute> 应用到 [Property 语句](/dotnet/visual-basic/language-reference/statements/property-statement) 中，而不是应用到 `Get` 或 `Set` 语句。  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 以指示符合或不符合。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [在 Visual Basic 中配置警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **错误 ID：**BC40043  
  
### 更正此错误  
  
-   从 `Get` 或 `Set` 语句中删除 <xref:System.CLSCompliantAttribute>。  
  
-   如果该属性应符合 CLS，则将 `Property` 语句标记为 `<CLSCompliant(True)>`。  
  
## 请参阅  
 [\<PAVE OVER\>编写符合 CLS 的代码](http://msdn.microsoft.com/zh-cn/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [Get 语句](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [Set 语句](/dotnet/visual-basic/language-reference/statements/set-statement)