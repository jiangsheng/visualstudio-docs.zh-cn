---
title: "在 Visual Studio 中安装 Python | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 066612a132bf6a092771afd5fc4a876d4b3be425
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="installing-python-support-in-visual-studio-on-windows"></a>在 Windows 上的 Visual Studio 中安装 Python 支持

若要安装针对 Visual Studio 的 Python 支持，请按照与你的 Visual Studio 版本匹配的部分中的说明进行操作：

- [Visual Studio 2017](#visual-studio-2017)
- [Visual Studio 2015](#visual-studio-2015)
- [Visual Studio 2013 及更早版本](#visual-studio-2013-and-earlier)

对于 Visual Studio 2015 及更早版本，还需要单独安装所选的 Python 解释器（Python 3.5 及更早版本；不支持 3.6）。 有关详细信息，请参阅 [Python 环境](python-environments.md)。 该页面还包含如何将现有 Python 解释器添加到 Visual Studio 2017 中的说明。

若要在执行安装步骤后快速测试 Python 支持，请按 Alt-I 并输入 `2+2` 打开 Python 交互式窗口。 如果看不到输出 `4`，请重新检查步骤。

> [!Tip]
> Python 工作负载包括有用的 Cookiecutter 扩展，扩展提供图形用户界面以发现模板、输入模板选项及创建项目和文件。 有关详细信息，请参阅[使用 Cookiecutter](cookiecutter.md)。

> [!Note]
> 目前尚未在 Visual Studio for Mac 中提供 Python 支持，但可在 Mac 和 Linux 上通过 Visual Studio Code 获取相应支持。 请参阅[问题和解答](python-in-visual-studio.md#questions-and-answers)。

## <a name="visual-studio-2017"></a>Visual Studio 2017

1. 下载并运行最新的 Visual Studio 2017 安装程序：

    > [!div class="nextstepaction"]
    > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">安装 Visual Studio 2017 Community</a>

    >[!Tip]
    > Community Edition 适用于个体开发者、课堂学习、学术研究和开放源代码开发。 对于其他用途，请安装 <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Professional</a> 或 <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Enterprise</a>。

1. 安装程序提供工作负载列表，即一组用于特定开发领域的相关选项。 对于 Python，请选择 **Python 开发**工作负载。

    ![Visual Studio 安装程序中的 Python 开发工作负载](media/installation-python-workload.png)

    可选：如果使用数据科学，还可考虑使用**数据科学和分析应用程序**工作负载。 此工作负载包含对 Python 以及 R 和 F# 语言的支持。 有关详细信息，请参阅[数据科学和分析应用程序工作负载](../rtvs/data-science-workload.md)。

    > [!Note]
    > Python 和数据科学工作负载仅可用于 Visual Studio 2017 版本 15.2 及更高版本。

1. 如果需要，选择安装程序右侧的其他选项。 跳过此步骤，接受默认选项。

    ![Visual Studio 安装程序中的 Python 开发选项](media/installation-python-options.png)

    | 选项 | 描述 | 
    | --- | --- |
    | Python 分发版本 | 选择计划使用的 Python 2、Python 3、Anaconda2 和 Anaconda3 分发版本的 32 位和 64 位变型的任意组合。 每个组合都包含分发版本的解释器、运行时和库。 其中 Anaconda 是一个开放数据科学平台，包含各种包。 （可随时返回 Visual Studio 安装程序来添加或删除分发版本。） |
    | Cookiecutter 模板支持 | 安装 Cookiecutter 图形用户界面，用于发现模板、输入模板选项以及创建项目和文件。 请参阅[使用 Cookicutter 扩展](cookiecutter.md)。 |
    | Python Web 支持 | 安装用于 Web 开发的工具（包括 HTML、CSS 和 JavaScript 编辑支持）以及用于使用 Bottle、Flask 和 Django 框架的项目的模板。 请参阅 [Python Web 项目模板](template-web.md)。 |
    | Python IoT 支持 | 支持使用 Python 开发 Windows IoT Core。 |
    | Python 本机开发工具 | 安装 C++ 编译器和其他必要组件用于开发 Python 本机扩展。 请参阅[创建适用于 Python 的 C++ 扩展](cpp-and-python.md)。 |
    | Azure 云服务核心工具 | 提供在 Python 中开发 Azure 云服务的其他支持。 请参阅 [Azure 云服务项目](template-azure-cloud-service.md)。 |

1. 安装后，安装程序会提供用于修改、启动、修复或卸载 Visual Studio 的选项。 如果有适用于任何已安装组件的 Visual Studio 更新可用，“修改”按钮会变为“更新”。 （随后在下拉菜单中提供修改选项。）还可搜索“Visual Studio”，从 Windows 开始菜单启动 Visual Studio 及安装程序。

    ![通过安装程序启动、修改或卸载 Visual Studio](media/installation-vs-launch.png)


> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Installing-Visual-Studio-Python-Support-go1id3LWE_1705918567]

## <a name="visual-studio-2015"></a>Visual Studio 2015

1. 通过“控制面板”>“程序和功能”，选择 **Microsoft Visual Studio 2015**，然后选择“更改”，从而运行 Visual Studio 安装程序。

1. 在安装程序中，选择“修改”。

1. 选择“编程语言”>“针对 Visual Studio 的 Python 工具”，然后选择“下一步”：

    ![Visual Studio 2015 安装程序中的 PTVS 选项](media/installation-vs2015.png)    

1. Visual Studio 安装程序完成后，[安装所选的 Python 解释器](python-environments.md#selecting-and-installing-python-interpreters)。 如果已安装了解释器，请参阅[为现有解释器创建环境](python-environments.md#creating-an-environment-for-an-existing-interpreter)。

## <a name="visual-studio-2013-and-earlier"></a>Visual Studio 2013 及更早版本

1. 为你的 Visual Studio 版本安装相应版本的针对 Visual Studio 的 Python 工具：

    - Visual Studio 2013：[Visual Studio 2013 PTVS 2.2](https://github.com/Microsoft/PTVS/releases/v2.2)。 Visual Studio 2013 中的“文件”>“新建项目”对话框提供用于此过程的快捷方式。
    - Visual Studio 2012：[Visual Studio 2012 PTVS 2.1](https://pytools.codeplex.com/downloads/get/920478)
    - Visual Studio 2010：[Visual Studio 2010 PTVS 2.1](https://pytools.codeplex.com/downloads/get/920479)

1. [安装所选的 Python 解释器](python-environments.md#selecting-and-installing-python-interpreters)。 如果已安装了解释器，请参阅[为现有解释器创建环境](python-environments.md#creating-an-environment-for-an-existing-interpreter)。

## <a name="install-locations"></a>安装位置

默认情况下，为计算机上的所有用户安装 Python 支持。

对于 Visual Studio 2017，Python 工作负载安装在 `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\<VS_edition>Common7\IDE\Extensions\Microsoft\Python` 中，其中 &lt;VS_edition&gt; 为社区版、专业版或企业版。

对于 Visual Studio 2015 及更早版本，安装路径如下所示：

- 32 位：
  - 路径：`%Program Files(x86)%\Microsoft Visual Studio <VS_ver>\Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`
  - 路径的注册表位置：`HKEY_LOCAL_MACHINE\Software\Microsoft\PythonTools\<VS_ver>\InstallDir`
- 64 位：
  - 路径：`%Program Files%\Microsoft Visual Studio <VS_ver>\Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`
  - 路径的注册表位置：`HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\PythonTools\<VS_ver>\InstallDir`

其中：

- &lt;VS_ver&gt; 是：    
    - Visual Studio 2015 14.0
    - Visual Studio 2013 12.0
    - Visual Studio 2012 11.0
    - Visual Studio 2010 10.0
- &lt;PTVS_ver&gt; 是版本号，例如 2.2、2.1、2.0、1.5、1.1 或 1.0。

### <a name="user-specific-installations-15-and-earlier"></a>特定于用户的安装（1.5 及更早版本）

仅允许为当前用户安装针对 Visual Studio 的 Python 工具 1.5 版及更早版本，这种情况下的安装路径是 `%LocalAppData%\Microsoft\VisualStudio\<VS_ver>\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`，其中 &lt;VS_ver&gt; 和 &lt;PTVS_ver&gt; 与上文所述相同。

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
