---
title: "图形诊断的工作方式 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ae14497-c77c-4399-bc0c-595caba23656
caps.latest.revision: 2
caps.handback.revision: 2
ms.author: "mithom"
manager: "douge"
---
# 图形诊断的工作方式
此处插入介绍。  
  
## 图形诊断的工作方式  
 要使用图形诊断，需要先记录有关应用程序如何在运行时使用 Direct3D API 的信息，然后检查记录的行为。  对于指定的帧，记录的信息包括 API 调用（例如清屏、绘制几何图形、调度计算着色器或更改图形设备状态的 API 调用）、API 调用的参数以及间接引用的缓冲区与对象的副本。  此外，与设置和初始化相关的 API 调用在任何帧呈现之前记录。  记录的信息将写入到图形日志 \(.vsglog\) 文件中。  
  
 可通过在开发计算机或者远程计算机或设备上播放图形事件来重新创建在图形日志中记录的呈现行为。  播放计算机可以是最初捕获图形日志的同一计算机或设备，也可以是不同计算机或设备。  对于大多数播放功能，播放计算机的图形硬件用于播放图形事件，但在使用 HLSL 调试器时，着色器代码始终通过使用 CPU 上的模拟 GPU 播放。  使用模拟 GPU 可以逐句通过着色器代码、检查变量和使用其他常见调试功能，而无论播放计算机中的图形硬件是否支持硬件调试。  
  
> [!NOTE]
>  虽然图形日志在内部捕获大部分相关信息，但仍需要更多信息才能完全使用某些图形诊断功能。  例如，若要完全利用图形调用堆栈功能，还必须具有程序数据库 \(.pdb\) 文件以及应用程序的源代码。  若要调试 HLSL 着色器源代码，还必须具有着色器源代码。  （如果着色器是通过 D3D11.1 着色器编译器来编译，并且调试信息已启用，则着色器源代码将在捕获期间嵌入到图形日志中。）  
  
> [!NOTE]
>  因为某些 API 可能在早期版本的 Windows 或 DirectX 中不可用，因此对于捕获了这些 API 调用的图形日志，你无法在不支持它们的播放计算机上播放它们。  
  
### 图形日志  
 图形日志包含从运行的 DirectX 图形应用程序中捕获的一个或多个帧。  图形日志是自包含日志，因此可在以后重新创建这些帧，并且无需外部信息或引用。  这意味着可以与其他开发人员共享图形日志、检查不同计算机上的问题以及检查旧图形日志（即使模型和纹理在开发过程中已更改）。  还可以同时加载多个图形日志 \(.vsglog\) 文件以比较数据和呈现结果。  
  
##### 打开图形日志 \(vsglog\) 文件  
  
1.  在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中的菜单栏上，依次选择**“文件”**、**“打开”**、**“文件”**。  此时将显示**“打开文件”**对话框。  
  
2.  指定要打开的图形日志 \(.vsglog\) 文件，然后选择**“打开”**按钮。  
  
> [!NOTE]
>  可以通过使用 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中的图形工具，从图形日志中提取和修改网格与纹理并保存其副本。  不过，图形日志的内容不受这些修改的影响。  有关这些图形工具的信息，请参阅[为游戏和应用程序使用三维资产](../designers/working-with-3-d-assets-for-games-and-apps.md)。