---
title: "SafeControls 元素 |Microsoft 文档"
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
helpviewer_keywords: SafeControls element
ms.assetid: f5ffdbbe-cf85-4e5a-9d39-3cd4462f2a0e
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 34ca67f0a256f48fc280a2f5545bf297cb41ed53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="safecontrols-element"></a>SafeControls 元素
  表示 ASPX 控件和指定为安全的任何用户访问 SharePoint 站点上的任意 ASPX 页上的 Web 部件的集合。  
  
## <a name="syntax"></a>语法  
  
```  
<SafeControls>  
  <SafeControl.../>  
</SafeControls>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[SafeControl](../sharepoint/safecontrol-element.md)|可选元素。<br /><br /> 表示一个 ASPX 控件或指定为安全的任何用户访问 SharePoint 站点上的任意 ASPX 页上的 Web 部件。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[项目项](../sharepoint/projectitem-element.md)|表示一个 SharePoint 项目项。 这是.spdata 文件的所需的根元素。|  
  
## <a name="remarks"></a>备注  
 安全控件有关的详细信息，请参阅[提供打包和部署信息在项目项中](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)。  
  
## <a name="element-information"></a>元素信息  
  
|||  
|-|-|  
|**命名空间**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**架构名称**|SharePoint 项目项架构|  
|**验证文件**|ProjectItemModelSchema.xsd|  
|**可以为空**|否|  
  
## <a name="see-also"></a>请参阅  
 [SharePoint 项目项架构参考](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [在项目项中提供打包和部署信息](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  