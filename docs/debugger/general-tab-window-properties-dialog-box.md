---
title: "常规选项卡，属性选项卡 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: Window Properties dialog box, General Tab
ms.assetid: 19142c60-9b32-46ba-a556-b62fd77568c1
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5aea8d5eb998280d6602f4ea28eb0b52d5f86da3
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2018
---
# <a name="general-tab-window-properties-dialog-box"></a>“窗口属性”对话框 ->“常规”选项卡
使用**常规**选项卡来显示有关所选的窗口的信息。 若要显示[窗口属性对话框](../debugger/window-properties-dialog-box.md)，焦点移到[Windows 视图](../debugger/windows-view.md)窗口。 在树中，选择任何窗口节点，然后选择**属性**从**视图**菜单。  
  
 以下设置子网上有**常规**选项卡：  
  
|条目|描述|  
|-----------|-----------------|  
|**窗口标题**|中的文本窗口标题中或包含在一个窗口中，如果它是控件的文本。|  
|**窗口句柄**|此窗口的唯一 ID。 窗口句柄数字会重复使用;它们仅针对该窗口的生存期标识一个窗口。|  
|**窗口进程**|此窗口的窗口过程函数虚拟地址。 此字段还指示此窗口是否是一个 Unicode 窗口中，以及是否是子类化。|  
|**矩形**|窗口边框。 也显示矩形的大小。 单位为像素屏幕坐标。|  
|**还原的矩形**|还原窗口边框。 也显示矩形的大小。 仅在最大化或最小化窗口时，还原的矩形将有所不同矩形。 单位为像素屏幕坐标。|  
|**客户端 Rect**|窗口客户端区域的边框。 也显示矩形的大小。 单位是像素窗口客户端区域的左上角相对。|  
|**实例句柄**|应用程序的实例句柄。 实例句柄不是唯一的。|  
|**控件 ID 或菜单句柄**|如果要显示的窗口是子窗口，将显示控件 ID 标签。 控件 ID 是一个整数，标识此子窗口的控件 id。 如果要显示的窗口不是子窗口，将显示的菜单句柄的标签。 菜单句柄是菜单的一个整数，标识与此窗口关联的句柄。|  
|**用户数据**|附加到此窗口结构的应用程序特定数据。|  
|**窗口字节**|与此窗口相关联的额外字节数。 这些字节的含义取决于应用程序。 展开该列表框，以查看 DWORD 格式中的字节值。|