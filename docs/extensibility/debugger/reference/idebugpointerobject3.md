---
title: "IDebugPointerObject3 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugPointerObject3 interface
ms.assetid: 11d26af4-1079-435e-96fa-d5269cbea8eb
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 228ac0317f9d65823839150f3e1dc69fd3feb25e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerobject3"></a>IDebugPointerObject3
> [!IMPORTANT]
>  在 Visual Studio 2015 中，已弃用这种方式实施表达式计算器。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)和[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 表示在分析树中，指向并扩展**IDebugPointerObject**接口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPointerObject3 : IDebugPointerObject  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 表达式计算器 (EE) 实现此接口。  
  
## <a name="methods"></a>方法  
 除了上的方法[IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetPointerAddress](../../../extensibility/debugger/reference/idebugpointerobject3-getpointeraddress.md)|检索的地址的指针。|  
  
## <a name="requirements"></a>惠?  
 标头： Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll