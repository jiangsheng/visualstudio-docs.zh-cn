---
title: "SignFile 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#SignFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, SignFile task
- SignFile task [MSBuild]
ms.assetid: edef1819-ddeb-4e09-95de-fc7063ba9388
caps.latest.revision: "19"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8c1e5e25d6a8b3b953d28676415266ccf245d418
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="signfile-task"></a>SignFile 任务
使用指定证书签署指定文件。  
  
## <a name="parameters"></a>参数  
 下表描述了 `SignFile` 任务的参数。  
  
 请注意：仅允许在具有 .NET 4.5 和更高版本的计算机上使用 SHA-256 证书。  
  
> [!WARNING]
>  自 Visual Studio 2013 Update 3 起，此任务有一个新的签名，使你可以指定文件的目标框架版本。 建议尽可能地使用此新签名，因为 MSBuild 过程只在目标框架为 .NET 4.5 或更高版本时使用 SHA-256 哈希。 如果目标框架是 .NET 4.0 或更低版本，将不使用 SHA-256 哈希。  
  
|参数|描述|  
|---------------|-----------------|  
|`CertificateThumbprint`|必选 `String` 参数。<br /><br /> 指定用于签名的证书。 此证书必须在当前用户的个人存储区中。|  
|`SigningTarget`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定要与证书一起签名的文件。|  
|`TimestampUrl`|可选 `String` 参数。<br /><br /> 指定时间戳服务器的 URL。|  
|`TargetFrameworkVersion`|用于目标的 .NET Framework 版本。|  
  
## <a name="remarks"></a>备注  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Utilities.Task> 类继承参数。 有关这些其他参数的列表及其说明，请参阅[任务基类](../msbuild/task-base-class.md)。  
  
## <a name="example"></a>示例  
 以下示例使用 `SignFile` 任务来签署 `FilesToSign` 项集合中指定的文件，使用的证书由 `Certificate` 属性定义。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.exe" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.5" />  
    </Target>  
</Project>  
```  
  
> [!NOTE]
>  证书指纹是该证书的 SHA-1 哈希。 有关详细信息，请参阅 [Obtain the SHA-1 Hash of a Trusted Root CA Certificate](http://msdn.microsoft.com/en-us/dd641990-9a88-4228-a245-017797131a87)（获取受信任的根 CA 证书的 SHA-1 哈希）。  
  
## <a name="example"></a>示例  
 以下示例使用 `Exec` 任务来签署 `FilesToSign` 项集合中指定的文件，使用的证书由 `Certificate` 属性定义。 你可用此在生成过程中对 Windows 安装程序文件进行签名。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.msi" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <Exec Command="signtool.exe sign /f CertFile /p Password "@(FileToSign)" "/>  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.0" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [任务参考](../msbuild/msbuild-task-reference.md)   
 [任务](../msbuild/msbuild-tasks.md)