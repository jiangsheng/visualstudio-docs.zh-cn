---
title: "如何：创建使用 Windows 窗体的工具箱控件 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "工具箱控件"
  - "winforms"
  - "工具箱"
ms.assetid: abbd3c3c-3a6e-4539-bd6c-a5891dead234
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 如何：创建使用 Windows 窗体的工具箱控件
借助 [!INCLUDE[vssdk_dev11_long](../misc/includes/vssdk_dev11_long_md.md)] 中内附的 Windows 窗体工具箱控件模板，你可以创建在安装扩展后自动添加到“工具箱”的 Windows 窗体控件。 本主题演示如何使用模板来创建可分配给其他用户的“工具箱”控件。  
  
> [!NOTE]
>  若要了解如何下载 Visual Studio SDK，请参阅 MSDN 网站上的 [Visual Studio 扩展性开发人员中心](http://go.microsoft.com/fwlink/?linkid=121964)。  
  
## 创建工具箱控件  
 使用 Windows 窗体工具箱控件模板创建项目，然后在设计器中生成用户界面 \(UI\)。  
  
#### 创建 Windows 窗体工具箱控件项目  
  
1.  在**“文件”**菜单上，单击**“新建”**，然后单击**“项目”**。  
  
2.  在“新建项目”对话框的“已安装模板”下，单击首选编程语言的节点，然后单击“扩展性”。 在项目类型列表中，选择“Windows 窗体工具箱控件”。  
  
3.  在“名称”框中，键入想要用于项目的名称。 单击“确定”。  
  
     Visual Studio 将创建一个解决方案，内含用户控件、将控件置于“工具箱”中的特性，以及用于部署的 VSIX 清单。  
  
#### 生成控件 UI  
  
1.  在“解决方案资源管理器”中双击 ToolboxControl.cs，以在设计器中打开它。  
  
2.  从“工具箱”中，将所需的任何控件拖动到设计界面，然后根据设计进行排列。  
  
3.  在“属性”窗口中，设置用户控件和子控件上的公共属性。  
  
## 编写控件的代码  
 默认情况下，你的控件将作为“工具箱”项组中的“ToolboxControl1”显示在“工具箱”中，其中此项组的名称与你解决方案的名称相同。 可在 ToolboxControl.cs 文件中更改这些名称。  
  
#### 编写控件的代码  
  
1.  在“解决方案资源管理器”中，右键单击 ToolboxControl.cs，然后单击“查看代码”以在代码视图中打开文件。  
  
2.  在实现控件的分部类定义处，右键单击类名，再单击“重构”，然后单击“重命名”。 控件安装后，将类名更改为你想要在“工具箱”中显示的名称。  
  
3.  在类定义正上方的 `ProvideToolboxControl` 特性声明中，将第一个参数的值更改为要在“工具箱”中托管此控件的项组的名称。  
  
     以下示例演示了 `General` 项组中名为 `Counter` 的控件的 `ProvideToolboxControl` 特性和调整后的类定义。  
  
     [!code-cs[ToolboxControlWinForms#07](../misc/codesnippet/CSharp/how-to-create-a-toolbox-control-that-uses-windows-forms_1.cs)]  
  
4.  实现控件的属性、方法和事件。  
  
## 生成、测试和部署  
 按 F5 生成项目（内附一个 .vsix 部署文件），并打开其“工具箱”中安装有控件的 Visual Studio 的第二个实例。  
  
#### 生成并测试控件  
  
1.  按 F5。  
  
2.  在 Visual Studio 的新实例中，创建 Windows 窗体应用程序项目。  
  
3.  在“工具箱”中查找控件，并将其拖动到设计图面上。  
  
4.  在“属性”窗口中，验证属性是否按预期方式显示。  
  
5.  添加测试方法和事件所需的任何代码或其他控件。  
  
6.  按 F5 键打开 Windows 窗体应用程序。  
  
7.  验证控件的属性、方法和的事件是否按预期运行。  
  
#### 部署控件  
  
1.  生成测试的项目后，打开文件资源管理器中项目的 \\bin\\debug\\ 文件夹，然后找到 .vsix 文件。  
  
2.  将 .vsix 文件上载到网络或网站。  
  
     若将文件上载到 [Visual Studio 库](http://go.microsoft.com/fwlink/?LinkID=123847) 网站，则其他用户可使用 Visual Studio 中的“扩展管理器”找到控件并将其安装。  
  
## 请参阅  
 [创建 WPF 工具箱控件](../extensibility/creating-a-wpf-toolbox-control.md)