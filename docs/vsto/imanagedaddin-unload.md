---
title: "IManagedAddin::Unload |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Unload method
ms.assetid: 40a73f07-2605-4745-8ac5-0a0189167fd7
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b16478232faa2b34a6d8f93d2a53b69b0f76b871
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imanagedaddinunload"></a>IManagedAddin::Unload
  只在托管 VSTO 外接程序卸载之前调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Unload();  
```  
  
## <a name="return-value"></a>返回值  
 HRESULT 值，指示方法是否已成功完成。  
  
## <a name="remarks"></a>备注  
 当前版本的 Microsoft Office 不调用此方法。 此方法保留供将来使用。  
  
## <a name="see-also"></a>请参阅  
 [IManagedAddin Interface](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Load](../vsto/imanagedaddin-load.md)  
  
  