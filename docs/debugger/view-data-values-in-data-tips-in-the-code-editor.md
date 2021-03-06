---
title: "在代码编辑器中查看数据提示中的数据值 |Microsoft 文档"
ms.custom: 
ms.date: 07/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], DataTips
- DataTips tool
ms.assetid: ffa7bd18-439b-4685-a9b3-c7884b5de41f
caps.latest.revision: "38"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 178bd1768474eaaaf760e2ef4feecfe0e1519bee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="view-data-values-in-datatips-in-the-code-editor"></a>在数据提示中在代码编辑器中查看数据值
使用数据提示功能，可以在调试期间方便地查看程序中变量的有关信息。 数据提示功能只能在中断模式下可用，并且只对当前执行范围内的变量有效。
  
### <a name="to-display-a-datatip"></a>显示数据提示  
  
1. 设置断点并开始调试 (按**F5**)。

2. 其中在调试器中暂停，将鼠标指针置于当前范围内的任何变量。
  
     屏幕上显示数据提示。
  
3.  移开鼠标指针时，数据提示会消失。 若要将固定数据提示，以便它保持打开状态，请单击**固定到源**图标或右键单击一个变量，然后单击**固定到源**。

    ![固定数据提示](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

    > [!NOTE]
    > 始终在挂起执行的上下文中（而不是在光标的悬停位置）计算数据提示。 如果将鼠标指针悬停在另一函数中的变量的上方（该变量与当前上下文中的某个变量同名），则另一函数中该变量的值将显示为当前上下文中的该变量的值。
  
### <a name="to-unpin-a-datatip-and-make-it-float"></a>解除固定数据提示，使其浮动  
  
-   在固定数据提示中，单击**从源**图标。  
  
     图钉图标将更改为解除固定位置。 现在，数据提示浮动在任何打开的窗口上方。 在调试会话结束时，浮动数据提示将关闭。  
  
### <a name="to-repin-a-floating-datatip"></a>重新固定浮动的数据提示  
  
-   在数据提示中，单击图钉图标。  
  
     图钉图标将更改为固定位置。 如果工具提示位于源窗口外部，将禁用图钉图标，因此将无法固定数据提示。  
  
### <a name="to-close-a-datatip"></a>关闭单个数据提示  
  
-   将鼠标指针放在数据提示中，并依次**关闭**图标。  
  
### <a name="to-close-all-datatips"></a>关闭所有数据提示  
  
-   上**调试**菜单上，单击**清除所有数据提示**。  
  
### <a name="to-close-all-datatips-for-a-specific-file"></a>关闭特定文件的所有数据提示  
  
-   上**调试**菜单上，单击**清除所有数据提示固定到***文件*。  
  
## <a name="expand-and-edit-information"></a>展开和编辑信息  
 利用数据提示功能，可以展开数组、结构或对象以查看其成员。 从数据提示还可以编辑变量的值。  
  
#### <a name="to-expand-a-variable-to-see-its-elements"></a>展开变量以查看它的元素  
  
-   在数据提示中，将鼠标指针置于 **+** 变量名之前的登录。  
  
    该变量展开以树的形式显示其元素。

    ![查看数据提示](../debugger/media/dbg-tour-data-tips.gif "查看数据提示")
  
    变量展开后，可以使用键盘上的箭头键进行上移或下移。 或者，也可使用鼠标。  
  
#### <a name="to-edit-the-value-of-a-variable-using-a-datatip"></a>使用数据提示功能编辑变量值  
  
1.  在数据提示中，单击值。 对于只读值，此功能是禁用的。  
  
2.  键入新值并按 Enter。  
  
## <a name="making-a-datatip-transparent"></a>使数据提示显示为透明  
 如果想要看到数据提示后面的代码，可以使数据提示暂时显示为透明。 这不适用于固定或浮动的数据提示。  
  
#### <a name="to-make-a-datatip-transparent"></a>使数据提示显示为透明  
  
-   在数据提示中，按 Ctrl。  
  
     在按住 Ctrl 键的时间内，数据提示将一直保持透明。  
  
## <a name="visualize-complex-data-types"></a>可视化复杂数据类型  
 如果数据提示中，一个或多个中的变量名旁边显示的放大镜图标[可视化工具](../debugger/create-custom-visualizers-of-data.md)，如[字符串可视化工具](../debugger/string-visualizer-dialog-box.md)，可用于该数据类型的变量。 您可以使用可视化工具以更直观的方式（通常为图形）显示信息。
  
#### <a name="to-view-the-contents-of-a-variable-using-a-visualizer"></a>使用可视化工具查看变量的内容  
  
-   单击放大镜图标![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "可视化工具图标")选择的数据类型的默认可视化工具。  
  
     或  
  
     单击可视化工具旁的弹出箭头，然后在适用于该数据类型的可视化工具列表中选择所需的可视化工具。  
  
     可视化工具将显示信息。  
  
## <a name="add-information-to-a-watch-window"></a>将信息添加到监视窗口  
 如果你想要继续观看列表视图中的变量，则可以添加到变量**监视**从数据提示窗口。  
  
#### <a name="to-add-a-variable-to-the-watch-window"></a>将变量添加到“监视”窗口  
  
-   右击数据提示中，，然后单击**添加监视**。  
  
     该变量添加到**监视**窗口。 如果你使用的版本支持多个**监视**windows，则变量添加到**监视 1。**  
  
## <a name="import-and-export-datatips"></a>导入和导出数据提示  
 您可以将数据提示导出到 XML 文件中，然后与同事共享该文件或使用文本编辑器编辑该文件。  
  
#### <a name="to-export-datatips"></a>导出数据提示  
  
1.  在调试菜单中，单击**导出数据提示**。  
  
     **导出数据提示**对话框随即出现。  
  
2.  使用标准文件技术导航到你想要保存 XML 文件中，键入的名称中的文件的位置**文件名**框中，并依次**确定**。  
  
#### <a name="to-import-datatips"></a>导入数据提示  
  
1.  在调试菜单中，单击**导入数据提示**。  
  
     **导入数据提示**对话框随即出现。  
  
2.  使用对话框中找到的 XML 文件，你想要打开，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [在调试器中查看数据](../debugger/viewing-data-in-the-debugger.md)   
 [监视和快速监视窗口](../debugger/watch-and-quickwatch-windows.md)   
 [创建自定义可视化工具](../debugger/create-custom-visualizers-of-data.md)   