---
title: "IDebugStackFrame2::GetThread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugStackFrame2::GetThread"
helpviewer_keywords: 
  - "IDebugStackFrame2::GetThread"
ms.assetid: cbeef85b-3dd7-4f97-adc2-c4d197d979fc
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugStackFrame2::GetThread
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

获取线程与堆栈帧。  
  
## 语法  
  
```cpp#  
HRESULT GetThread (   
   IDebugThread2** ppThread  
);  
```  
  
```c#  
int GetThread (   
   out IDebugThread2 ppThread  
);  
```  
  
#### 参数  
 `ppThread`  
 \[out\] 返回表示线程的 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 对象。  
  
## 返回值  
 如果成功，则返回; `S_OK`否则，返回错误代码。  
  
## 请参阅  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)