---
title: "IDiaSymbol::get_acceleratorPointerTags |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e5190496258cfb4ed66334e10a3d727a1c9555b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
对 c + + AMP 快捷键存根 （stub） 函数返回对应的所有快捷键指针标记值。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>参数  
 `cnt`  
 [in]输出数组的大小`pPointerTags`。  
  
 `pcnt`  
 [out]C + + AMP 快捷键存根 （stub） 函数中的加速器指针标记计数。  
  
 `pPointerTags`  
 [out]A`DWORD`用 c + + AMP 快捷键存根 （stub） 函数中的加速器指针标记值填充的数组指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="remarks"></a>备注  
 在调用此方法`IDiaSymbol`对应于 c + + AMP 快捷键存根 （stub） 函数的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)