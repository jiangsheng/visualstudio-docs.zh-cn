---
title: "错误： 用户无法执行存储过程 sp_enable_sql_debug |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.sqlde_accessdenied
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5da5a9aa6bc5f2bda382b69223b2b758f576ac29
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>错误：用户未能执行存储过程 sp_enable_sql_debug
在服务器上未能执行存储过程 sp_enable_sql_debug。 这可能是由于：  
  
-   连接问题。 需要有一个到服务器的稳定连接。  
  
-   在服务器上缺少必要的权限。 若要在 SQL Server 2005 上调试，运行 Visual Studio 的帐户和用于连接 SQL Server 的帐户都必须是 sysadmin 角色的成员。 用于连接 SQL Server 的帐户要么是 Windows 用户帐户（如果您正在使用 Windows 身份验证），要么是具有用户 ID 和密码的帐户（如果您使用 SQL 身份验证）。  
  
 有关详细信息，请参阅[如何： 为调试中设置 SQL Server 权限](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)。  
  
## <a name="see-also"></a>请参阅  
 [如何： 为调试设置 SQL Server 权限](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [设置 SQL 调试](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)