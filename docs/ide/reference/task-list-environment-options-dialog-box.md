---
title: "“选项”对话框 ->“环境”->“任务列表” | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.Task_List
- VS.ToolsOptionsPag.Environment.Task_List
- VS.ToolsOptionsPages.Environment.TaskList
- VS.Environment.Task List
helpviewer_keywords:
- Token List
- tokens
- icons, in Task List
- Task List, customizing environment
- Options dialog box, Task List environment
- exclamation points
- comments, comment tasks in Task List
- tokens, and the Task List
- Task List, comment tasks
ms.assetid: 88327e04-fa3e-48db-995b-ad89e0dc4ed2
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b6f8adfd3ce7d585cffe3c7506c4fdd56cad4a11
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="task-list-environment-options-dialog-box"></a>“选项”对话框 ->“环境”->“任务列表”
该选项页允许添加、删除和更改生成“任务列表”提醒的注释标记。 要显示这些设置，请从“工具”菜单选择“选项”，展开“环境”文件夹，然后选择“任务列表”。  
  
## <a name="task-list-options"></a>任务列表选项  
 确认删除任务  
 选中后，任何时候从“任务列表”删除用户任务时都会显示一个消息框，用来确认删除。 默认情况下选择此选项。  
  
> [!NOTE]
>  若要删除任务注释，使用该链接查找注释，然后将其从你的代码中删除。  
  
 仅显示文件名  
 选中后，“任务列表”的“文件”列只显示要进行编辑的文件名，而不是其完整路径。  
  
## <a name="tokens"></a>标记  
 将注释插入代码（其文本以“标记列表”中的某个标记开头）中时，“任务列表”会在该文件每次打开以进行编辑时，将注释显示为新项。 可以单击此“任务列表”项以直接跳转到代码中的注释行。 有关详细信息，请参阅[使用任务列表](../../ide/using-the-task-list.md)。  
  
 标记列表  
 显示标记列表，并允许你添加或删除自定义标记。 注释标记在 Visual C# 和 Visual C++ 中要区分大小写，但在 Visual Basic 中不区分大小写。  
  
> [!NOTE]
>  如果未按标记在“标记列表”中显示的样子键入所需标记，那么注释任务不会在“任务列表”中显示。  
  
 优先级  
 设置使用所选标记的任务的优先级。 将在“任务列表”中为以此标记开头的任务注释自动分配指定的优先级。  
  
 name  
 输入标记字符串。 这一操作会启用“添加”按钮。 在“添加”按钮上，此字符串包含在“标记列表”中，而以此名称开头的注释将显示在“任务列表”中。  
  
 添加  
 输入新名称时将启用。 单击可使用在“名称”和“优先级”字段中输入的值添加新的标记字符串。  
  
 删除  
 单击可从“标记列表”中删除选定标记。 无法删除默认注释标记。  
  
 更改  
 单击可使用在“名称”和“优先级”字段中输入的值更改现有标记。  
  
> [!NOTE]
>  无法重命名或删除默认注释标记，但可以更改其优先级别。  
  
## <a name="see-also"></a>请参阅  
 [使用任务列表](../../ide/using-the-task-list.md)   
 [在代码中设置书签](../../ide/setting-bookmarks-in-code.md)   
 [“选项”对话框 ->“环境”](../../ide/reference/environment-options-dialog-box.md)