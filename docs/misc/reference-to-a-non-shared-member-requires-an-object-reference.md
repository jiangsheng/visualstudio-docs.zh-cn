---
title: "对非共享成员的引用需要对象引用 | Microsoft Docs"
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
  - "bc30469"
  - "vbc30469"
helpviewer_keywords: 
  - "BC30469"
ms.assetid: af503e8b-2e1f-4f91-a07f-b1ddd73dd4a6
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 对非共享成员的引用需要对象引用
你引用了代码内的非共享成员，且未能应用对象引用。 类名本身不能用于限定非共享的成员。 必须先将实例声明为对象变量，然后由变量名称引用。  
  
 **错误 ID：**BC30469  
  
### 更正此错误  
  
1.  将实例声明为对象变量。  
  
2.  用变量名称引用实例。  
  
## 请参阅  
 [不在生成中：了解类](http://msdn.microsoft.com/zh-cn/cc2355a2-cb98-4353-9440-736585aec46c)   
 [不在生成中：Visual Basic 中的共享成员](http://msdn.microsoft.com/zh-cn/dbc3783f-83a2-4225-995d-c2d6d025663d)   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)   
 [NOTINBUILD：当多个变量具有相同名称时解析引用](http://msdn.microsoft.com/zh-cn/9601e39f-1911-44e1-ace5-3f6e090408b9)