---
title: "UnregisterAssembly 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#UnregisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UnregisterAssembly task
- UnregisterAssembly task [MSBuild]
ms.assetid: 04f549dd-3591-4dda-9c3a-cf6ede9df2c3
caps.latest.revision: 21
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 79460291e91f0659df0a4241e17616e55187a0e2
ms.openlocfilehash: 9f2973dcb28338d26b0c3372a95d166d1b2170a0
ms.lasthandoff: 02/22/2017

---
# <a name="unregisterassembly-task"></a>UnregisterAssembly 任务
注销用于 COM 互操作的指定程序集。 执行 [RegisterAssembly 任务](../msbuild/registerassembly-task.md)的相反任务。  
  
## <a name="parameters"></a>参数  
 下表描述了 `UnregisterAssembly` 任务的参数。  
  
|参数|说明|  
|---------------|-----------------|  
|`Assemblies`|可选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定要注销的程序集。|  
|`AssemblyListFile`|可选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 包含有关 `RegisterAssembly` 任务和 `UnregisterAssembly` 任务之间状态的信息。 这样可以防止任务尝试注销无法在 `RegisterAssembly` 任务中注册的程序集。<br /><br /> 如果已指定此参数，则 `Assemblies` 和 `TypeLibFiles` 参数将被忽略。|  
|`TypeLibFiles`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 从指定的程序集中注销指定的类型库。 **注意：**只有当类型库文件名不同于程序集名称时，此参数才是必需的。|  
  
## <a name="remarks"></a>备注  
 此任务的成功对是否存在程序集不作要求。 如果尝试注销不存在的程序集，则该任务将成功并且出现警告。 发生这种情况是因为此任务的工作就是从注册表中删除程序集注册。 如果该程序集不存在，则它不在注册表中，因此，任务将成功完成。  
  
 除了上面列出的参数，此任务还从 <xref:Microsoft.Build.Tasks.AppDomainIsolatedTaskExtension> 类继承参数，此类本身继承自 <xref:System.MarshalByRefObject> 类。 `MarshalByRefObject` 类提供的功能与 <xref:Microsoft.Build.Utilities.Task> 类的相同，但该功能可以在其自己的应用程序域中进行实例化。  
  
## <a name="example"></a>示例  
 以下示例使用 `UnregisterAssembly` 任务注销 `OutputPath` 和 `FileName` 属性指定的路径处的程序集（如果存在）。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <OutputPath>\Output\</OutputPath>  
        <FileName>MyFile.dll</FileName>  
    </PropertyGroup>  
    <Target Name="UnregisterAssemblies">  
        <UnregisterAssembly  
            Condition="Exists('$(OutputPath)$(FileName)')"  
            Assemblies="$(OutputPath)$(FileName)" />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>另请参阅  
 [RegisterAssembly 任务](../msbuild/registerassembly-task.md)   
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)