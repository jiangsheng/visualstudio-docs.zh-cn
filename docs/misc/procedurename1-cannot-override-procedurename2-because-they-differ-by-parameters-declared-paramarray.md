---
title: "&lt;procedurename1&gt; 无法重写 &lt;procedurename2&gt;，因为它们在声明为“ParamArray”的参数上存在差异 | Microsoft Docs"
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
  - "bc30906"
  - "vbc30906"
helpviewer_keywords: 
  - "BC30906"
ms.assetid: 12939030-732e-4c6d-8fe9-707b7532174b
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;procedurename1&gt; 无法重写 &lt;procedurename2&gt;，因为它们在声明为“ParamArray”的参数上存在差异
派生类中的过程重写基类中同名的过程，但参数列表不同。  
  
 要重写继承类中的过程，重写过程必须与其参数列表、访问级别和返回类型（如果有）匹配。 特别是，它必须与所有 [Optional](/dotnet/visual-basic/language-reference/modifiers/optional) 或 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray) 声明匹配。  
  
 **错误 ID：**BC30906  
  
### 更正此错误  
  
-   如果想要重写过程，请将参数列表设置为与基类过程中的参数列表完全相同。 如果最后一个参数使用基类过程中的 `ParamArray` 进行声明，则使用重写过程中的 `ParamArray` 声明。  
  
-   如果希望参数列表与基类版本不同，则不能重写它。 请考虑改为重载。 有关更多信息，请参见[过程重载](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)。  
  
## 请参阅  
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [不在生成中：重写属性和方法](http://msdn.microsoft.com/zh-cn/2167e8f5-1225-4b13-9ebd-02591ba90213)