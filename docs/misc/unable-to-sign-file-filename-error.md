---
title: "无法对文件“&lt;filename&gt;”进行签名：&lt;error&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31028"
  - "vbc31028"
helpviewer_keywords: 
  - "BC31028"
ms.assetid: 2cb22e75-5ee2-4e07-afc0-680a0bd543d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法对文件“&lt;filename&gt;”进行签名：&lt;error&gt;
尝试对指定文件进行签名时出错。 发生此错误可能有几个原因：  
  
-   没有足够的权限。  
  
-   缺少 Authenticode 签名所需的系统文件。  
  
-   引用了不存在的证书或私钥文件。  
  
-   文件名或 URL 拼写不正确。  
  
 **错误 ID：**BC31028  
  
### 更正此错误  
  
1.  输入正确的证书和私钥文件名。  
  
2.  如果使用 Authenticode 签名，请检查 Signcode.exe 和 Javasign.dll 文件是否存在，且未设置其只读特性。  
  
3.  请确保你对文件具有 `Write` 权限。  
  
## 请参阅  
 [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/zh-cn/2d299154-34ea-41ba-ad12-17075bb7e1db)   
 [Deployment and Authenticode Signing](http://msdn.microsoft.com/zh-cn/ecc3f059-da2e-445b-9b87-5b2978e2f8b2)