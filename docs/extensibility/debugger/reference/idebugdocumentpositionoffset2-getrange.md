---
title: "IDebugDocumentPositionOffset2::GetRange |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 09b415e01b6c768f471bdf9ad2e595d1a910d582
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
检索当前的文档位置的范围。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRange(  
   DWORD* pdwBegOffset,  
   DWORD* pdwEndOffset  
);  
```  
  
```csharp  
public int GetRange(  
   ref uint pdwBegOffset,  
   ref uint pdwEndOffset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwBegOffset`  
 [在中，out]为范围的开始位置偏移量。 如果不需要此信息，请将此参数设置为 null 值。  
  
 `pdwEndOffset`  
 [在中，out]偏移量范围的结束位置。 如果不需要此信息，请将此参数设置为 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 在一个位置断点的文档位置中指定的范围是调试引擎 (DE) 用于搜索提前实际影响代码的语句。 例如，考虑以下代码：  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 第 5 行分配给正在调试的程序的任何代码。 如果第 5 行设置断点调试器想 DE 向前搜索一定影响代码的第一行，调试器会指定一系列，包括的其他候选行断点可能正确放置。 DE 将然后向前搜索这些行直到它找到可以接受断点的行。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)   
 [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)