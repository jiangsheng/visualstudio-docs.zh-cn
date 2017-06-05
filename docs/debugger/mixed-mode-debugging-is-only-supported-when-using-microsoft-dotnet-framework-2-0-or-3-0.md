---
title: "仅当使用 Microsoft .NET Framework 2.0 或 3.0 时才支持混合模式调试 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.interop_unsupported_to_old"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 仅当使用 Microsoft .NET Framework 2.0 或 3.0 时才支持混合模式调试
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

低于 2.0 的 Microsoft .NET Framework 版本不支持对 64 位进程进行混合模式调试。  这意味着，当您进行调试时，无法从托管代码单步执行到本机代码，也无法从本机代码单步执行到托管代码。  
  
 若要解决此问题，您可以：  
  
-   更新项目以使用 Microsoft .NET Framework 2.0 或 3.0。  
  
-   在单独的调试会话中调试托管代码和本机代码。  
  
-   作为 32 位进程调试混合代码，如下面的过程所述。  
  
### 将操作系统更改为 32 位（Visual Basic 或 C\#）  
  
1.  在**“解决方案资源管理器”**中，右击所需项目，然后在快捷方式菜单中单击**“属性”**。  
  
2.  在属性页中，单击**“编译”**或**“调试”**选项卡。  
  
3.  单击**“平台”**，然后从平台列表中选择**“x86”**。  
  
     默认情况下，Visual Basic 和 C\# 编译器生成要在任何 CPU 上运行的代码。  在 64 位计算机上，这些二进制代码作为 64 位进程运行。  若要在 32 位进程中运行，必须选择**“Win32”**而不是**“AnyCPU”**。  
  
### 将操作系统更改为 32 位 \(C\/C\+\+\)  
  
1.  在**“解决方案资源管理器”**中，右击所需项目，然后在快捷方式菜单中单击**“属性”**。  
  
     在属性页中，单击**“平台”**，然后从平台列表中选择**“Win32”**。  
  
### 更正此错误  
  
-   请参见[Setting Up SQL Debugging](http://msdn.microsoft.com/zh-cn/3db09e68-edcc-42de-9c22-4e97cfd55ab3)。  
  
## 请参阅  
 [调试 64 位应用程序](../debugger/debug-64-bit-applications.md)