---
title: "没有鼠标 | Microsoft Docs"
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
  - "vbrMouse_NoMouseIsPresent"
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 没有鼠标
调用了 `My.Computer.Mouse` 对象的一个属性，但是计算机未安装鼠标或鼠标端口。  
  
### 更正此错误  
  
-   在调用周围将 `Try...Catch` 块添加到 `My.Computer.Mouse` 对象的属性。  
  
     — 或 —  
  
-   在计算机上安装鼠标。  
  
## 请参阅  
 [My.Computer.Mouse 对象](/dotnet/visual-basic/language-reference/objects/my-computer-mouse-object)   
 [Visual Basic 中的异常与错误处理](http://msdn.microsoft.com/zh-cn/3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally 语句](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)