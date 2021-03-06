---
title: "Idiadatasource:: Get_lasterror |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1a8320a78c807f08d24f6bcc41db9d775850101b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
检索最后一个的加载错误的文件名称。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 pRetVal  
 [out]返回包含与最后一个的加载错误关联的.pdb 文件名称的字符串。  
  
## <a name="return-value"></a>返回值  
 返回负载操作而引起的最后一个错误代码。 返回`E_INVALIDARG`如果`pRetVal`参数是`NULL`。  
  
## <a name="example"></a>示例  
  
```C++  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>请参阅  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)