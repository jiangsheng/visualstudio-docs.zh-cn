---
title: "在 Visual Studio 中标识并自定义键盘快捷方式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Environment.Keyboard
helpviewer_keywords:
- keyboard shortcuts [Visual Studio], customizing
- importing shortcut keys [Visual Studio]
- shortcut key combinations [Visual Studio]
- commands [Visual Studio], shortcut keys
- custom shortcut keys [Visual Studio]
- customizing keyboard shortcuts [Visual Studio]
- exporting shortcut keys [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7258a1ba99764fa7af7ce73874f447db99b8b168
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="identifying-and-customizing-keyboard-shortcuts-in-visual-studio"></a>在 Visual Studio 中标识并自定义键盘快捷键

你可以认识 Visual Studio 命令的键盘快捷键，自定义这些快捷键并将其导出以供他人使用。 许多快捷键总是调用相同的命令，但是，快捷键的行为可能因以下条件而异：

- 你首次运行 Visual Studio（例如，常规开发或 Visual C#）时选择了哪些默认环境设置。

- 你是否已自定义快捷键的行为。

- 你选择快捷键时所在的上下文。 例如，你使用设置设计器时，F2 快捷键将调用“编辑.编辑单元格”命令；而你使用团队资源管理器时，则调用“文件.重命名”命令。

不管设置、自定义和上下文，始终可以在“选项”对话框中找到并更改键盘快捷方式。 还可以在[常用命令的默认键盘快捷方式](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md)中查找诸多命令的默认键盘快捷方式，并可在[默认键盘快捷方式](../ide/default-keyboard-shortcuts-in-visual-studio.md)中查找所有默认快捷方式（基于常规开发设置）的完整列表。

如果一个快捷键仅分配给全局上下文中的一个命令，则该快捷键将始终调用该命令。 但是，一个快捷键可以同时分配给全局上下文和特定上下文中的不同命令。 如果你在特定上下文中使用这个快捷键，则该快捷键将调用特定上下文中的命令，而非全局上下文中的命令。

> [!NOTE]
> 你的 Visual Studio 设置和版本可能会更改对话框中显示的菜单命令和选项的名称和位置。 本主题基于“常规开发设置”。

## <a name="identifying-a-keyboard-shortcut"></a>认识键盘快捷键

1. 在菜单栏上，依次选择“工具” 、“选项” 。

2. 展开“环境”，然后选择“键盘”。

   ![在“选项”对话框中显示键盘快捷方式](../ide/media/optionskeyboard.png "OptionsKeyboard")

3. 在“显示命令包含”框中输入命令的完整或部分名称，不含空格。

   例如，可查找 `solutionexplorer` 的命令。

4. 在列表中选择正确的命令。

    例如，可以选择“View.SolutionExplorer”。

5. 如果该命令有键盘快捷方式，则显示在“选定命令的快捷方式”列表中。

   ![查看指定命令的快捷方式](../ide/media/viewshortcut.png "ViewShortcut")

## <a name="customizing-a-keyboard-shortcut"></a>自定义键盘快捷键

1. 在菜单栏上，依次选择“工具” 、“选项” 。

2. 展开“环境”文件夹，然后选择“键盘”。

3. 可选：在“显示命令包含”框中输入命令的完整或部分名称，不含空格，以此来筛选命令列表。

4. 在列表中选择要为其分配键盘快捷键的命令。

在“新快捷方式用于”列表中，选择希望在其中使用该快捷方式的功能区。

    For example, you can choose **Global** if you want the shortcut to work in all contexts. You can use any shortcut that isn't mapped (as Global) in another editor. Otherwise, the editor overrides the shortcut.

    > [!NOTE]
    > You can't assign the following keys as part of a keyboard shortcut in **Global**: Print Scrn/Sys Rq, Scroll Lock, Pause/Break, Tab, Caps Lock, Insert, Home, End, Page Up, Page Down, the Windows logo key, the Application key, any of the Arrow keys, or Enter; Num Lock, Delete, or Clear on the numeric keypad; the Ctrl+Alt+Delete key combination.

6. 在“按快捷键”框中，输入要使用的快捷方式。

    > [!NOTE]
    > 你可以创建将字母与 Alt 键和/或 Ctrl 键相结合的快捷键。 你也可以创建将 Shift 键和字母与 Alt 键和/或 Ctrl 键相结合的快捷键。

     如果快捷方式已分配给另一个命令，则显示在“快捷方式的当前使用对象”框中。 在这种情况下，按 Backspace 键删除该快捷键，然后再尝试另一个。

    ![为命令指定不同的快捷方式](../ide/media/reassignshortcut.png "ReassignShortcut")

7. 选择“分配”按钮。

    > [!NOTE]
    > 如果为命令指定不同的快捷方式，则选择“分配”按钮，然后选择“取消”按钮，对话框随即关闭，但是更改不会撤消。

## <a name="sharing-custom-keyboard-shortcuts"></a>共享自定义键盘快捷键

你可以共享你的自定义键盘快捷键，方法是将其导出到文件中，然后将文件提供给他人，以便他们导入数据。

### <a name="to-export-only-keyboard-shortcuts"></a>仅导出键盘快捷键

1. 在菜单栏上，选择“工具”、“导入和导出设置”。

2. 选择“导出选定的环境设置”，然后选择“下一步”按钮。

3. 在“要导出哪些设置?”下，清除“所有设置”复选框，展开“选项”，然后展开“环境”。

4. 选中“键盘”复选框，然后选择“下一步”按钮。

    ![仅导出自定义的键盘快捷方式](../ide/media/exportshortcuts.png "ExportShortcuts")

5. 在“要如何命名你的设置文件?”和“在此目录中存储我的设置文件”框中，保留默认值或指定其他值，然后选择“完成”按钮。

    默认情况下，你的快捷键保存在 %USERPROFILE%\Documents\Visual Studio 2017\Settings 文件夹下的文件中。 文件名称将反映你导出设置的日期，扩展名为 .vssettings。

### <a name="to-import-only-keyboard-shortcuts"></a>仅导入键盘快捷键

1. 在菜单栏上，选择“工具”、“导入和导出设置”。

2. 选择“导入选定的环境设置”选项按钮，然后选择“下一步”按钮。

3. 选择“否，仅导入新设置，覆盖我的当前设置”选项按钮，然后选择“下一步”按钮。

4. 在“我的设置”下，选择包含要导入的快捷方式的文件，或选择“浏览”按钮定位到正确的文件。

5. 选择“下一步”按钮。

6.  在“要导入哪些设置?”下，清除“所有设置”复选框，展开“选项”，然后展开“环境”。

7. 选中“键盘”复选框，然后选择“完成”按钮。

    ![仅导入自定义的键盘快捷方式](../ide/media/importshortcuts.png "ImportShortcuts")

## <a name="see-also"></a>请参阅

[Visual Studio 的辅助功能](../ide/reference/accessibility-features-of-visual-studio.md)