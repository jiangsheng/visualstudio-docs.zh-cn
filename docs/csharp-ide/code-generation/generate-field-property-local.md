---
title: "生成字段、 属性或本地的代码生成 (C#) |Microsoft 文档"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 85d15d28fae994f029e678183d2f08d561c70f1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-field-property-or-local-in-c"></a>在 C# 中生成字段、 属性或本地 #
**新增功能：**便会立即生成以前未声明的字段、 属性或本地的代码。 

**何时：**你键入时引入新字段、 属性或本地并想要正确地将其，自动声明。  

**原因：**无法使用它，但是此功能将生成声明并自动键入先声明字段、 属性或本地。 

**如何：**

1. 将光标置于该行上存在红色波形曲线，该值指示你已使用本地的字段或属性不存在的情况。

   ![突出显示的代码](media/field_highlight.png)

1. 接下来，请执行以下任一操作：
   * **键盘**
     * 按**Ctrl +。** 向触发器**快速操作和重构**菜单，然后选择**生成字段/属性/本地**从预览窗口弹出窗口。
   * **鼠标**
     * 右键单击并选择**快速操作和重构**菜单，然后选择**生成字段/属性/本地**从预览窗口弹出窗口。
     * 将鼠标悬停在红色波形曲线和单击 ![灯泡](media/bulb.png) 显示的图标。
     * 单击 ![灯泡](media/bulb.png) 如果文本光标已在行中使用红色波形曲线的左边距中显示的图标。

   ![生成字段/属性/本地预览](media/field_preview.png)

   >[!TIP]
   >使用[**预览更改**](../../ide/preview-changes.md)底部的预览窗口来查看所有将在你的选择之前所做的更改的链接。

1. 使用推断出的类型从其使用情况将自动创建的字段、 属性或本地。

   ![生成字段/属性/本地结果](media/field_result.png)

## <a name="see-also"></a>请参阅  
[代码生成 (C#)](../code-generation-csharp.md)  
[预览更改](../../ide/preview-changes.md) 
