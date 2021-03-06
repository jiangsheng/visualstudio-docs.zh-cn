---
title: "“Microsoft.VisualBasic.ComClassAttribute”的容器“&lt;classname2&gt;”未声明为“Public”，因此不能应用于“&lt;classname1&gt;” | Microsoft Docs"
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
  - "vbc32504"
  - "bc32504"
helpviewer_keywords: 
  - "BC32504"
ms.assetid: 4138b639-88d6-4b51-afcd-c92a1be36f1c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “Microsoft.VisualBasic.ComClassAttribute”的容器“&lt;classname2&gt;”未声明为“Public”，因此不能应用于“&lt;classname1&gt;”
在不为 `Public` 的类中声明了使用 `COMClassAttribute` 特性块的类。 如果将类公开为 COM 对象，必须使用 `Public` 访问来声明其整个包含层次结构。  
  
 **错误 ID：**BC32504  
  
### 更正此错误  
  
-   声明所有包含类 `Public`，或删除 `COMClassAttribute` 特性块。  
  
## 请参阅  
 [不在生成中：Visual Basic 中使用的特性](http://msdn.microsoft.com/zh-cn/22231318-8a40-49af-9245-e0aab723563b)   
 [不在生成中：特性的应用程序](http://msdn.microsoft.com/zh-cn/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute 类](http://msdn.microsoft.com/zh-cn/5c2f0835-9210-47dc-bc59-5c1769953574)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)