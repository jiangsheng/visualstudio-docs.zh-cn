---
title: "编译器警告（等级 1）CS1634 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1634"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1634"
ms.assetid: 4fd00eeb-89e3-4c18-827d-9b00a4bd8c9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 编译器警告（等级 1）CS1634
应为 disable 或 restore  
  
 如果 \#pragma 警告子句格式有误，例如忽略了禁用或还原，将出现此错误。 有关详细信息，请参阅 [\#pragma warning](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) 主题。  
  
## 示例  
 下面的示例生成 CS1634：  
  
```  
// CS1634.cs // compile with: /W:1 #pragma warning   // CS1634 // Try this instead: // #pragma warning disable 0219 class MyClass { public static void Main() { } }  
```