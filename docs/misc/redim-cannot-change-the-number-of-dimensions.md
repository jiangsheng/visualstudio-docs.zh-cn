---
title: "“ReDim”无法更改维数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrArray_RankMismatch"
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# “ReDim”无法更改维数
某操作尝试使用 `ReDim` 更改数组的秩（维数）。`ReDim` 可以更改已形式声明的数组的一个或多个维度的大小，但它不能更改数组的秩。  
  
### 更正此错误  
  
-   确保想要更改的是数组的秩而不是其维度的大小，尽可能使用 `Dim` 声明具有所需秩的新数组。  
  
## 请参阅  
 [NOTINBUILD Visual Basic 中的数组概述](http://msdn.microsoft.com/zh-cn/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [NOTINBUILD Visual Basic 中的多维数组](http://msdn.microsoft.com/zh-cn/d92cad25-07e2-4d79-8ea4-ab269700f5de)   
 [ReDim 语句](/dotnet/visual-basic/language-reference/statements/redim-statement)   
 [Dim 语句](/dotnet/visual-basic/language-reference/statements/dim-statement)