---
title: "生成的类或类型的代码生成 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: ebc361fe-d9b1-4c7a-ae28-5e71b5775460
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vsl.GenerateFromUsage
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: a0a900b912c1a15c61dc17164571c1284743581c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-class-or-type-in-visual-basic"></a>在 Visual Basic 中生成的类或类型
**新增功能：**便会立即生成的类或类型的代码。 

**何时：**引入的新类或类型并且想要正确地将其，自动声明。  

**原因：**无法再使用它，但此功能将生成类，或键入自动声明的类或类型。 

**如何：**

1. 将光标放在行上： 有红色的波浪线，该值指示你已使用尚不存在的类。

   ![突出显示的代码](media/class_highlight.png)

1. 接下来，请执行以下任一操作：
   * **键盘**
     * 按**Ctrl +。** 向触发器**快速操作和重构**菜单并选择一个预览窗口弹出窗口中的选项。
   * **鼠标**
     * 右键单击并选择**快速操作和重构**菜单并选择一个预览窗口弹出窗口中的选项。
     * 将鼠标悬停在红色波形曲线和单击 ![灯泡](media/bulb.png) 显示的图标。
     * 单击 ![灯泡](media/bulb.png) 如果文本光标已在行中使用红色波形曲线的左边距中显示的图标。

   ![生成类预览](media/class_preview.png)

   选择 | 描述
   --- | ---
   生成类的*TypeName*新文件中 | 创建一个名为类*TypeName*中名为的文件*TypeName*.cs/.vb
   生成类的*TypeName* | 创建一个名为类*TypeName*当前文件中。
   生成嵌套的类*TypeName* | 创建一个名为类*TypeName*嵌套在当前类。
   生成新类型... | 使用你指定的属性的所有创建的新类或结构。

   >[!TIP]
   >使用[**预览更改**](../../ide/preview-changes.md)底部的预览窗口来查看所有将在你的选择之前所做的更改的链接。

1. 如果你选择**生成新类型...**项，将弹出对话框，您可以执行一些其他操作。

   ![生成类型](media/class_newtype.png)

   选择 | 描述
   --- | ---
   Access | 将类型设置为具有*默认*，*内部*或*公共*访问。
   类型 | 这可以设置为*类*或*结构*。
   name | 这不能更改，将已键入的名称。
   项目 | 如果你的解决方案中有多个项目，你可以选择想类/结构生存。
   文件名 | 可以创建新文件，也可以将类型添加到现有文件。

1. 类/结构将使用从用法推断构造函数自动创建。

   ![生成类结果](media/class_result.png)

## <a name="see-also"></a>请参阅  
[代码生成 (Visual Basic)](../code-generation-vb.md)  
[预览更改](../../ide/preview-changes.md)