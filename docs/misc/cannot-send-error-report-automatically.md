---
title: "不能自动发送错误报告 | Microsoft Docs"
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
  - "bc2027"
  - "vbc2027"
helpviewer_keywords: 
  - "BC2027"
ms.assetid: 84ba8580-2234-46d1-b4a5-94b03f64c0c7
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 不能自动发送错误报告
不能自动发送错误报告。 请访问“http:\/\/go.microsoft.com\/fwlink\/?LinkId\=42039”以配置“发送错误报告”设置。  
  
 已指定 `/errorreport:send` 编译器选项，但未将计算机配置为自动发送错误报告。 不会发送有关 Visual Basic 编译器中内部错误的信息。  
  
 **错误 ID：**BC2027  
  
### 更正此错误  
  
-   删除 `/errorreport:send` 编译器选项，或将其替换为 `/errorreport:queue``/errorreport:prompt` 或 `/errorreport:none`。  
  
     — 或 —  
  
-   按照 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=42039](http://go.microsoft.com/fwlink/?LinkId=42039) 中的说明启用自动错误报告。  
  
## 请参阅  
 [\/errorreport](/dotnet/visual-basic/reference/command-line-compiler/errorreport)   
 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=42039](http://go.microsoft.com/fwlink/?LinkId=42039)