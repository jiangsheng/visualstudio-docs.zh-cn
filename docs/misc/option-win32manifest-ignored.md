---
title: "/win32manifest 选项已忽略 | Microsoft Docs"
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
  - "vbc2034"
  - "bc2034"
helpviewer_keywords: 
  - "BC2034"
ms.assetid: 8009553a-f6ba-4d2b-8ddd-8a9357bc928e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32manifest 选项已忽略
已忽略 \/win32manifest 选项。 只有在目标是程序集时才能指定该选项。  
  
 当 `/target` 选项设置为 `module` 时，已向 Visual Basic 编译器传递 `/win32manifest` 编译器选项。  
  
 **错误 ID：**BC2034  
  
### 更正此错误  
  
1.  删除 `/win32manifest` 编译器选项或将 `/target` 选项设为 `exe`、`winexe` 或 `library`。  
  
## 请参阅  
 [\/target](/dotnet/visual-basic/reference/command-line-compiler/target)   
 [\/win32manifest](/dotnet/visual-basic/reference/command-line-compiler/win32manifest)   
 [Visual Basic 命令行编译器](/dotnet/visual-basic/reference/command-line-compiler/index)