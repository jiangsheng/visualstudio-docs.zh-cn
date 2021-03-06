---
title: "Office 编程中的常见任务 |Microsoft 文档"
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
helpviewer_keywords:
- Office development in Visual Studio, getting started
- FAQs (frequently asked questions) [Office development in Visual Studio]
- Office development in Visual Studio, frequently asked questions
ms.assetid: 7afc9bad-1d31-486e-beea-91e6d308cd67
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9f3ed53011bca8d3ab7aa4f9d6be8e619ce1b8b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="common-tasks-in-office-programming"></a>Office 编程中的常规任务
  本主题旨在帮助针对使用 Visual Studio 对 Office 解决方案编程的下列常见问题找到解决方法。  
  
-   [安装和常规任务](#projects)。  
  
-   [用户界面自定义任务](#ui)。  
  
-   [Excel 自动化任务](#excel)。  
  
-   [Word 自动化任务](#word)。  
  
-   [数据任务](#data)。  
  
-   [服务器端文档管理任务](#server)。  
  
-   [安全性任务](#security)。  
  
-   [部署任务](#deployment)。  
  
##  <a name="projects"></a> Setup and General Tasks  
  
-   [如何： 在 Visual Studio 中创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
-   [如何：升级 Office 解决方案](http://msdn.microsoft.com/en-us/a269e539-b717-4680-a568-2152b070347e)。  
  
-   [How to: Install Office Primary Interop Assemblies](../vsto/how-to-install-office-primary-interop-assemblies.md)。  
  
-   [How to: Target Office Applications Through Primary Interop Assemblies](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)。  
  
-   [如何： 在 Office 项目中创建事件处理程序](../vsto/how-to-create-event-handlers-in-office-projects.md)。  
  
-   [How to: Open Office Solutions without Running Code](../vsto/how-to-open-office-solutions-without-running-code.md)。  
  
-   [How to: Set Up Configuration Information for an Office Solution](../vsto/how-to-set-up-configuration-information-for-an-office-solution.md)。  
  
-   [How to: Show the Developer Tab on the Ribbon](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)。  
  
-   [How to: Show Add-in User Interface Errors](../vsto/how-to-show-add-in-user-interface-errors.md)。  
  
##  <a name="ui"></a> User Interface Customization Tasks  
  
### <a name="controls-on-documents-and-worksheets"></a>文档和工作表中的控件  
  
-   [How to: Add Windows Forms Controls to Office Documents](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)。  
  
-   [How to: Add NamedRange Controls to Worksheets](../vsto/how-to-add-namedrange-controls-to-worksheets.md)。  
  
-   [How to: Add ListObject Controls to Worksheets](../vsto/how-to-add-listobject-controls-to-worksheets.md)。  
  
-   [How to: Add Windows Forms Controls to Office Documents](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)。  
  
-   [How to: Add Content Controls to Word Documents](../vsto/how-to-add-content-controls-to-word-documents.md)。  
  
-   [How to: Add Bookmark Controls to Word Documents](../vsto/how-to-add-bookmark-controls-to-word-documents.md)。  
  
### <a name="task-panes-in-document-level-customizations"></a>文档级自定义项中的任务窗格  
  
-   [如何： 将操作窗格添加到 Word 文档或 Excel 工作簿](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)。  
  
### <a name="task-panes-in-vsto-add-ins"></a>VSTO 外接程序中的任务窗格  
  
-   [How to: Add a Custom Task Pane to an Application](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)。  
  
### <a name="ribbon-customizations"></a>功能区自定义项  
  
-   [How to: Get Started Customizing the Ribbon](../vsto/how-to-get-started-customizing-the-ribbon.md)。  
  
-   [如何： 更改的功能区上的选项卡位置](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)。  
  
-   [How to: Customize a Built-in Tab](../vsto/how-to-customize-a-built-in-tab.md)。  
  
-   [如何： 将控件添加到 Backstage 视图](../vsto/how-to-add-controls-to-the-backstage-view.md)。  
  
-   [How to: Export a Ribbon from the Ribbon Designer to Ribbon XML](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)。  
  
### <a name="outlook-form-regions"></a>Outlook 窗体区域  
  
-   [How to: Add a Form Region to an Outlook Add-in Project](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)。  
  
-   [How to: Prevent Outlook from Displaying a Form Region](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)。  
  
### <a name="custom-menus"></a>自定义菜单  
  
-   [如何： 向快捷菜单添加命令](../vsto/how-to-add-commands-to-shortcut-menus.md)。  
  
##  <a name="excel"></a> Excel Automation Tasks  
  
-   [如何： 以编程方式在工作表单元格中显示字符串](../vsto/how-to-programmatically-display-a-string-in-a-worksheet-cell.md)。  
  
-   [如何： 以编程方式创建新的工作簿](../vsto/how-to-programmatically-create-new-workbooks.md)。  
  
-   [如何： 以编程方式打开工作簿](../vsto/how-to-programmatically-open-workbooks.md)。  
  
-   [如何： 以编程方式保存工作簿](../vsto/how-to-programmatically-save-workbooks.md)。  
  
-   [如何： 以编程方式关闭工作簿](../vsto/how-to-programmatically-close-workbooks.md)。  
  
-   [如何： 以编程方式将新工作表添加到工作簿](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)。  
  
-   [如何： 以编程方式隐藏工作表](../vsto/how-to-programmatically-hide-worksheets.md)。  
  
-   [如何： 以编程方式移动在工作簿中的工作表](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)。  
  
-   [如何： 以编程方式保护工作簿](../vsto/how-to-programmatically-protect-workbooks.md)。  
  
-   [如何： 以编程方式引用代码中的工作表范围](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)。  
  
-   [如何： 以编程方式将样式应用于工作簿中](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)。  
  
-   [如何： 以编程方式更改包含选定单元格的工作表行中格式设置](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)。  
  
-   [如何： 以编程方式搜索中工作表范围内的文本](../vsto/how-to-programmatically-search-for-text-in-worksheet-ranges.md)。  
  
-   [如何： 以编程方式打印工作表](../vsto/how-to-programmatically-print-worksheets.md)。  
  
-   [如何： 以编程方式进行 Excel 计算](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)。  
  
-   [如何： 以编程方式在工作表中的数据排序](../vsto/how-to-programmatically-sort-data-in-worksheets.md)。  
  
##  <a name="word"></a> Word Automation Tasks  
  
-   [如何： 以编程方式创建新文档](../vsto/how-to-programmatically-create-new-documents.md)。  
  
-   [如何： 以编程方式打开现有文档](../vsto/how-to-programmatically-open-existing-documents.md)。  
  
-   [如何： 以编程方式保存文档](../vsto/how-to-programmatically-save-documents.md)。  
  
-   [如何： 以编程方式关闭文档](../vsto/how-to-programmatically-close-documents.md)。  
  
-   [如何： 以编程方式在 Word 文档中插入文本](../vsto/how-to-programmatically-insert-text-into-word-documents.md)。  
  
-   [如何： 以编程方式定义和选择文档中的范围](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)。  
  
-   [如何： 以编程方式在 Word 中的重置范围文档](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)。  
  
-   [如何： 以编程方式设置的文档中的文本格式](../vsto/how-to-programmatically-format-text-in-documents.md)。  
  
-   [How to: Add XMLNode Controls to Word Documents](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)。  
  
-   [如何： 以编程方式更新书签文本](../vsto/how-to-programmatically-update-bookmark-text.md)。  
  
-   [如何： 以编程方式搜索和替换文档中的文本](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)。  
  
-   [如何： 以编程方式打印文档](../vsto/how-to-programmatically-print-documents.md)。  
  
-   [如何： 以编程方式创建 Word 表](../vsto/how-to-programmatically-create-word-tables.md)。  
  
-   [如何： 以编程方式向 Word 表中添加行和列](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)。  
  
-   [如何： 以编程方式统计文档中的字符](../vsto/how-to-programmatically-count-characters-in-documents.md)。  
  
##  <a name="data"></a> Data Tasks  
  
### <a name="data-bound-controls"></a>数据绑定控件  
  
-   [How to: Populate Worksheets with Data from a Database](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)。  
  
-   [How to: Populate Documents with Data from a Database](../vsto/how-to-populate-documents-with-data-from-a-database.md)。  
  
-   [How to: Populate Documents with Data from Services](../vsto/how-to-populate-documents-with-data-from-services.md)。  
  
-   [How to: Populate Documents with Data from Objects](../vsto/how-to-populate-documents-with-data-from-objects.md)。  
  
-   [How to: Populate Documents with Data from a Database](../vsto/how-to-populate-documents-with-data-from-a-database.md)。  
  
-   [How to: Populate Documents with Data from Services](../vsto/how-to-populate-documents-with-data-from-services.md)。  
  
-   [How to: Update a Data Source with Data from a Host Control](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)。  
  
### <a name="cached-data-in-document-level-solutions"></a>文档级解决方案中的缓存数据  
  
-   [How to: Cache Data for Use Offline or on a Server](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)。  
  
-   [How to: Programmatically Cache a Data Source in an Office Document](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)。  
  
-   [How to: Cache Data in a Password-Protected Document](../vsto/how-to-cache-data-in-a-password-protected-document.md)。  
  
### <a name="custom-xml-data"></a>自定义 XML 数据  
  
-   [How to: Add Custom XML Parts to Document-Level Customizations](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)。  
  
-   [How to: Add Custom XML Parts to Documents by Using VSTO Add-Ins](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)。  
  
##  <a name="server"></a> Server-side Document Management Tasks  
  
-   [如何： 从文档中删除托管的代码扩展](../vsto/how-to-remove-managed-code-extensions-from-documents.md)。  
  
-   [如何： 将托管的代码扩展附加到文档](../vsto/how-to-attach-managed-code-extensions-to-documents.md)。  
  
##  <a name="security"></a> Security Tasks  
  
-   [如何： 登录 Office 解决方案](../vsto/how-to-sign-office-solutions.md)。  
  
##  <a name="deployment"></a> Deployment Tasks  
  
-   [如何：使用 ClickOnce 发布 Office 解决方案](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)。  
  
-   [如何：使用 ClickOnce 将文档级 Office 解决方案发布到 SharePoint 服务器](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58)。  
  
-   [如何：安装 ClickOnce Office 解决方案](http://msdn.microsoft.com/en-us/14702f48-9161-4190-994c-78211fe18065)。  
  
-   [如何：在最终用户计算机上安装必备组件以运行 Office 解决方案](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98)。  
  
-   [如何：为部署 Office 解决方案准备 IIS](http://msdn.microsoft.com/en-us/f62bce70-81d4-4f8b-86e6-2f2afec5d9b4)。  
  
-   [如何：更新部署的 Office 解决方案](http://msdn.microsoft.com/en-us/be96db53-b6ea-46ab-b8d9-b76b098b3b13)。  
  
-   [如何：更改 Office 解决方案的安装路径](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd)。  
  
## <a name="see-also"></a>请参阅  
 [入门 &#40; Visual Studio &#41; 中的 Office 开发](../vsto/getting-started-office-development-in-visual-studio.md)   
 [按 Office 应用程序和项目类型提供的功能](../vsto/features-available-by-office-application-and-project-type.md)   
 [Office 开发示例和演练](../vsto/office-development-samples-and-walkthroughs.md)  
  
  