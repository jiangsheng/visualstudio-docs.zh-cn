---
title: "移植、迁移和升级 Visual Studio 项目 | Microsoft Docs"
ms.custom: 
ms.date: 07/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Win8ExpressDesktopBlock
- w8trefactor
- VS.ReviewProjectAndSolutionChangesDialog.UpgradeRetarget
- ProjectCompatibilityDlgHelpTopic
- VS.ReviewProjectAndSolutionChangesDialog.Upgrade
helpviewer_keywords:
- conversion, projects
- asset compatibility
- projects, conversion
ms.assetid: bee759bd-6ff5-4c2e-913a-ea7d3c906c29
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: b508aadfb44792374c323854ee5333905827f23e
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>移植、迁移和升级 Visual Studio 项目

Visual Studio 的每个版本通常都支持大部分以前的项目、文件和其他资产类型。 可以[照常](../ide/solutions-and-projects-in-visual-studio.md)使用这些类型。如果不依赖新功能，Visual Studio 可保留与旧版本（如 Visual Studio 2015、Visual Studio 2013 和 Visual Studio 2012）的向后兼容性。 （若要了解哪些功能特定于哪个版本，请参阅[发行说明](https://www.visualstudio.com/vs/release-notes/)。）

但是，在以后对某些类型的支持会改变。 较新版本的 Visual Studio 可能不再支持某些类型，或者不再要求迁移或更新这些类型，使其不再向后兼容。 有关迁移问题的当前状态，请参阅 [Visual Studio 开发人员社区站点](https://developercommunity.visualstudio.com)。

> [!Important]
> 当前主题仅提供 Visual Studio 2017 中涉及迁移的项目类型的相关详细信息。 其中不包括没有迁移问题的受支持项目类型；在[平台目标以及兼容性](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs)中可以找到该列表。 另请注意，某些项目类型在 Visual Studio 2017 中完全不受支持，因此不能迁移。

> [!Important]
> 打开某些项目类型需要在 Visual Studio 安装程序中添加相应的工作负载。 如果尚未安装工作负荷，Visual Studio 将报告未知的或不兼容的项目类型。 在这种情况下，请检查安装选项，然后重试。 同样，有关 Visual Studio 2017 中项目支持的详细信息，请参阅[平台目标以及兼容性](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs)。

## <a name="projects"></a>项目

以下列表描述了 Visual Studio 2017 中对在之前版本中创建的项目的支持。

如果在此处未看到任何项目或文件类型（此处本应出现这些内容），请参阅[本主题的 Visual Studio 2015 版本](port-migrate-and-upgrade-visual-studio-projects.md)并在下面的注释中记录。

| 项目类型 | 支持 |
| --- | --- |
| .NET Core 项目 (.xproj) | 使用 Visual Studio 2015 旧预览工具创建的项目，其中包括 .xproj 项目文件。 使用 Visual Studio 2017 打开 .xproj 文件时，系统将提示将该文件迁移到 .csproj 格式（执行 .xproj 文件的备份）。 VS2015 及早期版本中不支持 .NET Core 项目的这种 .csproj 格式。  Visual Studio 2017 不支持 .xproj 格式，除非迁移到 .csproj 格式。 有关详细信息，请参阅[将 .NET Core 项目迁移到 .csproj 格式](https://docs.microsoft.com/dotnet/core/migration/#visual-studio-2017)。|
| ASP.NET Web 应用程序和启用了 Application Insights 的 ASP.NET Core Web 应用程序 | 对于每个 Visual Studio 用户，资源信息存储在每个用户实例的注册表中。 用户未打开项目，但想要搜索 Azure Application Insights 数据时，可使用此项。 Visual Studio 2015 使用与 Visual Studio 2017 不同的注册表位置，且未发生冲突。<br/><br/>用户创建 ASP.NET Web 应用程序或 ASP.NET Core Web 应用程序后，资源存储在 .suo 文件中。 用户可在 Visual Studio 2015 或 2017 中打开项目，只要 Visual Studio 支持这两个版本中使用的项目和解决方案，资源信息就可用于这两个版本。 用户需要在每个产品上进行一次身份验证。 例如，如果使用 Visual Studio 2015 创建项目，然后在 Visual Studio 2017 中打开，则用户需要在 Visual Studio 2017 上进行身份验证。 |
| C#/Visual Basic Web 窗体或 Windows 窗体 | 可以在 Visual Studio 2017 和 Visual Studio 2015 中打开项目。 |
| 数据库单元测试项目（.csproj、.vbproj）    | 较旧的数据单元测试项目将在 Visual Studio 2017 中加载，但将使用 GAC 版本的依赖关系。 若要升级单元测试项目以使用最新的依赖关系，请在“解决方案资源管理器”中右键单击该项目，然后选择“转换为 SQL Server 单元测试项目...”。 |
| F# | Visual Studio 2017 可以打开 Visual Studio 2013 和 2015 中创建的项目。 但是，若要在这些项目中启用 Visual Studio 2017 功能，请打开项目属性，将目标 fsharp.core 更改为 F# 4.1。 此外，还需注意，.NET 工作负载不会默认选择 Visual Studio 安装程序中的“F# 语言支持”选项；必须为工作负载选择该选项，或从“开发活动”下的“个人组件”选项卡中选择该选项。 |
| InstallShield<br/>MSI 安装程序 | 借助 [Visual Studio 安装程序项目扩展](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects)，在 Visual Studio 2010 中创建的安装程序项目可在更高版本中打开。 另请参阅 [WiX Toolset Visual Studio 2017 Extension](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)（WiX 工具集 Visual Studio 2017 扩展）。 Visual Studio 不再附带 InstallShield Limited Edition。 有关 Visual Studio 2017 的可用性，请咨询 [Flexera 软件](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio)。 |
| LightSwitch | Visual Studio 2017 中不再支持 LightSwitch。 使用 Visual Studio 2012 及早期版本创建并在 Visual Studio 2013 或 Visual Studio 2015 中打开的项目将进行升级，之后只能在 Visual Studio 2013 或 Visual Studio 2015 中打开。 |
| Microsoft Azure Tools for Visual Studio | 若要打开这些类型的项目，请首先安装 [Azure SDK for .NET](http://azure.microsoft.com/downloads/)，然后打开该项目。 如有必要，请更新项目。 |
| 模型-视图-控制器框架 (ASP.NET MVC) | 对 MVC 版本和 Visual Studio 的支持：<ul><li>Visual Studio 2010 SP1 支持 MVC 2 和 MVC 3；通过[ASP.NET 4 MVC 4 for Visual Studio 2010 SP1 下载](https://www.microsoft.com/download/details.aspx?id=30683)添加 MVC 4 支持</li><li>Visual Studio 2012 仅支持 MVC 3 和 MVC 4</li><li>Visual Studio 2013 仅支持 MVC 4 和 MVC 5</li><li>Visual Studio 2017 和 Visual Studio 2015 支持 MVC 4（可打开现有项目但无法创建新项目）和 MVC 5</li></ul><br/><br/>升级 MVC 版本：<ul><li>有关如何从 MVC 2 自动升级到 MVC 3 的信息，请参阅 [ASP.NET MVC 3 应用程序升级程序](http://go.microsoft.com/fwlink/?LinkID=238178)。</li><li>有关如何从 MVC 2 手动升级到 MVC 3 的信息，请参阅 [将 ASP.NET MVC 2 项目升级到 ASP.NET MVC 3 Tools 更新](http://go.microsoft.com/fwlink/?linkid=238178)。</li><li>有关如何从 MVC3 手动升级到 MVC 4 的信息，请参阅 [将 ASP.NET MVC 3 项目升级到 ASP.NET MVC 4](http://www.asp.net/whitepapers/mvc4-release-notes)。 如果你的项目以 .NET Framework 3.5 SP1 为目标，则必须重定目标才能使用 .NET Framework 4。</li><li>有关如何从 MVC 4 手动升级到 MVC 5 的信息，请参阅 [How to Upgrade an ASP.NET MVC 4 and Web API Project to ASP.NET MVC 5 and Web API 2](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2)（如何将 ASP.NET MVC 4 和 API.NET 项目升级到 ASP.NET MVC 5 和 Web API 2）</li></ul> |
| 建模 | 如果允许 Visual Studio 自动更新项目，则可以在 Visual Studio 2015、Visual Studio 2013 或 Visual Studio 2012 中打开该项目。<br/><br/>Visual Studio 2015 和 Visual Studio 2017 之间未更改建模项目的格式，并且项目可以在任一版本中打开和修改。 但是，Visual Studio 2017 中的行为具有差异：<ul><li>建模项目现被称为菜单和模板中的“依赖关系验证”项目。</li><li>Visual Studio 2017 中不再支持 UML 关系图。 UML 文件照常在解决方案资源管理器中列出，但将以 XML 文件形式打开。 使用 Visual Studio 2015 查看、创建或编辑 UML 关系图。</li><li>在 Visual Studio 2017 中，生成建模项目时不再验证体系结构依赖关系。 但将在生成每个代码时进行验证。 此更改不会影响建模项目，但它需要对所验证的代码项目进行更改。 Visual Studio 2017 可以自动对代码项目执行必要的更改（[详细信息](http://go.microsoft.com/fwlink/?LinkId=827800)）。</li></ul> |
| MSI 安装程序 (.vdproj) | 请参阅上面的 InstallShield 项目。 | 
| Office 2007 VSTO | 需要 Visual Studio 2017 单向升级。 |
| Office 2010 VSTO | 如果项目面向 .NET Framework 4，则可以在 Visual Studio 2010 SP1 及更高版本中打开此项目。 所有其他项目需要单向升级。 |
| SharePoint 2010 | 使用 Visual Studio 2017 打开 SharePoint 解决方案项目时，它将升级到 SharePoint 2013 或 SharePoint 2016。 “.NET 桌面开发”工作负载必须安装于 Visual Studio 2017 中，以便升级。<br/><br/>若要深入了解如何升级 SharePoint 项目，请参阅 [Upgrade to SharePoint 2013](https://technet.microsoft.com/library/cc303420.aspx)（升级到 SharePoint 2013）、[Update Workflow in SharePoint Server 2013](https://technet.microsoft.com/library/dn133867.aspx)（更新 SharePoint 2013 中的工作流）和 [Create the SharePoint Server 2016 farm for a database attach upgrade](https://technet.microsoft.com/library/cc263026(v=office.16).aspx)（创建 SharePoint Server 2016 场用于数据库附加升级）。 |
| SharePoint 2016 | 不能在 Visual Studio 2017 中打开 Office 开发人员工具预览版 2 中创建的 SharePoint 外接程序项目。 若要解决此问题，需要在 `.csproj` 或 `.vbproj` 文件中将 `MinimumVisualStudioVersion` 更新到 12.0 并将 `MinimumOfficeToolsVersion` 更新到 12.2。 |
| Silverlight | Visual Studio 2017 不支持 Silverlight 项目。 若要继续使用 Silverlight 应用程序，请继续使用 Visual Studio 2015。 |
| SQL Server Reporting Services 和 SQL Server Analysis Services（SSRS、SSDT、SSAS、MSAS） | 通过 Visual Studio 库中的两个扩展来提供对这些项目类型的支持：[Microsoft Analysis Services 建模项目](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects)和 [Microsoft Reporting Services 项目](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio)。 Visual Studio 2017 的数据存储和处理工作负载中还包括 SSDT 支持。 |
| SQL Server Integration Services (SSIS) | 尚不提供对 Visual Studio 2017 的支持。 以后将在 [SQL Server Integration Services 博客](https://blogs.msdn.microsoft.com/ssis/)上宣布提供支持。 目前对 SSIS 的建议是继续使用 Visual Studio 2015。 |
| Visual C++ | 你可以使用 Visual Studio 2017 打开在 Visual Studio 2015 中原样创建的解决方案和项目，但在较旧版本的 Visual Studio 中创建的项目可能需要升级项目或重定向到较新的工具集才能使用 Visual Studio 2017 生成。 有关详细信息，请参阅 [Visual C++ 移植和升级指南](https://docs.microsoft.com/cpp/porting/visual-cpp-porting-and-upgrading-guide)。 |
| Visual Studio 扩展性/VSIX | 将更新 MinimumVersion 14.0 或更低版本中的项目以声明 MinimumVersion 15.0，这样可防止在早期版本的 Visual Studio 中打开该项目。 若要允许在早期版本中打开项目，请将 MinimumVersion 设置为 `$(VisualStudioVersion)`。 另请参阅[如何：将扩展性项目迁移到 Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)。 |
| Visual Studio 实验室管理工具版 | 你可以使用 Microsoft 测试管理器或 Visual Studio 2010 SP1 及更高版本打开在以上任一版本中创建的环境。 但对于 Visual Studio 2010 SP1，在可以创建环境之前，Microsoft 测试管理器的版本必须与 Team Foundation Server 的版本匹配。 |
| Visual Studio Tools for Apache Cordova |可以在 Visual Studio 2017 中打开此项目，但此项目不具有向后兼容性。 从 Visual Studio 2015 中打开某个项目时，系统将提示允许修改项目。 这会将项目升级为使用工具集而非 `taco.json` 文件管理 Cordova 库、该库的平台和插件以及该库的节点/npm 依赖关系的版本控制。 有关详细信息，请参阅[迁移指南](https://docs.microsoft.com/visualstudio/cross-platform/tools-for-cordova/first-steps/migrate-from-visual-studio-2015)。 |
| Windows Communication Foundation, Windows Workflow Foundation | 可以在 Visual Studio 2017、Visual Studio 2015、Visual Studio 2013 和 Visual Studio 2012 中打开此项目 |
| Windows Presentation Foundation | 可以在 Visual Studio 2013、Visual Studio 2012 和 Visual Studio 2010 SP1 中打开此项目。 |
| Windows 应用商店/手机应用 | Visual Studio 2017 不支持 Windows Store 8.1 和 8.0 的项目，也不支持 Windows Phone 8.1 和 8.0 的项目。 若要继续使用这些应用，请继续使用 Visual Studio 2015。 若要继续使用 Windows Phone 7.x 项目，请使用 Visual Studio 2012。 |
