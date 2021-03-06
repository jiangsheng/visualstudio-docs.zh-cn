---
title: "Visual Studio 中的模板发现故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 72663d56844fcc34164e9408ab14c8ead234683e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="troubleshooting-template-installation"></a>模板安装疑难解答

如果在部署项目或项模板的问题，你可以启用诊断日志记录。

1. 在其中创建 pkgdef 文件 Common7\IDE\CommonExtensions 文件夹安装 (例如 C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef) 包含以下内容：

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. 打开"开发人员命令提示"你的安装通过在 Windows 搜索中，搜索并运行`devenv /updateConfiguration`。

1. 启动 Visual Studio 并启动新项目和新项对话框，以便初始化两个模板树。 模板日志现在将出现在**%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** （instanceid 对应于你的 Visual Studio 实例的安装 ID）。 每个模板树初始化附加到此日志条目。

日志文件包含以下列：

- **FullPathToTemplate**，它具有以下值：

    - 基于清单的部署的 1

    - 基于磁盘的部署的 0

- **TemplateFileName**

- 其他模板属性

> [!NOTE]
> 若要禁用日志记录，请删除该 pkgdef 文件，或更改的值`EnableTemplateDiscoveryLog`到`dword:00000000`，然后运行`devenv /updateConfiguration`试。

## <a name="see-also"></a>请参阅

[创建自定义项目和项模板](creating-custom-project-and-item-templates.md)