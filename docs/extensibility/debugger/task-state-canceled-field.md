---
title: "TASK_STATE_CANCELED 字段 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TASK_STATE_CANCELED field, Task class [.NET Framework debug engines]
ms.assetid: f4f5a96a-8230-493d-9696-8d2716bda261
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a6f37c397ec7dab6095cb03e2b93cb8f65892091
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="taskstatecanceled-field"></a>TASK_STATE_CANCELED 字段
它已达到运行状态，或它已对其取消和完成没有出现异常之前，该任务已取消。  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
 由于无法访问此内部成员在.NET Framework 中，以下语法提供共同点中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.field static assembly literal int32 TASK_STATE_CANCELED = int32(0x00800000)  
```  
  
## <a name="remarks"></a>备注  
 如果[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)字段包含此值，<xref:System.Threading.Tasks.Task.Status%2A>属性返回<xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>。  
  
## <a name="see-also"></a>请参阅  
 [任务类](../../extensibility/debugger/task-class-internal-members.md)