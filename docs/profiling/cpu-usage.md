---
title: "分析 Visual Studio 中的 CPU 使用率 | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7501a20d-04a1-480f-a69c-201524aa709d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eabbb315d03a6ba69d80d46276b0b6dff5846693
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="analyze-cpu-usage"></a>分析 CPU 的使用量
如需调查应用中的性能问题，最好从了解其使用 CPU 的方式开始。 **CPU 使用率** 工具可显示 CPU 耗用时间执行 Visual C++、Visual C#/Visual Basic 和 JavaScript 代码的位置。 从 Visual Studio 2015 Update 1 开始，不离开调试器即可查看每个函数的 CPU 使用率细目。 可以在调试时打开和关闭 CPU 分析，并在停止执行时（例如在断点处）查看结果。  
  
有多个选项可用于运行和管理诊断会话。 例如，你可以在本地或远程计算机上或在模拟器或仿真程序中运行“CPU 使用率”  工具。 可以分析在 Visual Studio（附加在运行的应用上）中打开的项目的性能，或启动从 Microsoft 官方商城安装的应用。 有关详细信息，请参阅[使用或不使用调试器运行分析工具](../profiling/running-profiling-tools-with-or-without-the-debugger.md)。 有关分析 UWP 应用性能的演练，请参阅[分析通用 Windows 应用 (UWP) 中的 CPU 使用率](analyze-cpu-usage-in-a-windows-universal-app.md)。 

在这里，我们将向你演示如何使用发行版本收集和分析 CPU 使用率。 若要在调试时分析 CPU 使用率，请参阅[性能分析初学者指南](../profiling/beginners-guide-to-performance-profiling.md)。 
  
##  <a name="BKMK_Collect_CPU_usage_data"></a> 收集 CPU 使用量数据  
  
1.  在 Visual Studio 中，将解决方案配置设置为“零售”  ，然后选择部署目标。  
  
     ![选择发布和本地计算机](../profiling/media/cpuuse_selectreleaselocalmachine.png "CPUUSE_SelectReleaseLocalMachine")  
  
    -   在“发布”  模式下运行应用能更清晰地看到实际的应用性能。  
  
    -   在本地计算机上运行应用可最佳复制安装的应用的执行过程。  
  
    -   如果从远程设备收集数据，则可直接在该设备上运行应用，而不通过使用远程桌面连接运行。  
  
    -   对于 Windows Phone 应用，直接从“设备”  收集数据这种方式提供的数据最准确。  
  
2.  在“调试”  菜单上，选择“性能探查器...” 。  
  
3.  选择“CPU 使用率”  ，然后选择“启动” 。  
  
     ![选择 CPU 使用率](../profiling/media/cpuuse_lib_choosecpuusage.png "CPUUSE_LIB_ChooseCpuUsage")  
  
4.  启动应用时，单击“获取最大数” 。 显示输出后等待约 1 秒时间，然后选择“获取最大数，异步” 。 在单击按钮之间进行停顿有助于更轻松地隔离诊断报告中的按钮单击例程。  
  
5.  在第二个输出行显示之后，在性能和诊断中心中选择 **“停止收集”** 。  
  
 ![停止 CpuUsage 数据收集](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 CPU 使用量工具可分析数据并显示报告。  
  
 ![CpuUsage 报告](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
## <a name="analyze-the-cpu-usage-report"></a>分析 CPU 使用量报告  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a> CPU 使用率调用关系树  
 若要开始了解调用关系树的信息，重新选择 `GetMaxNumberButton_Click` 段，查看调用关系树的详细信息。  
  
####  <a name="BKMK_Call_tree_structure"></a>调用关系树结构  
 ![GetMaxNumberButton_Click 调用关系树](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![第 1 步](../profiling/media/procguid_1.png "ProcGuid_1")|CPU 使用量调用关系树中的顶级节点是一个伪节点|  
|![第 2 步](../profiling/media/procguid_2.png "ProcGuid_2")|在大多数应用中，当禁用 **“显示外部代码”** 选项时，二级节点是 **[外部代码]** 节点，该节点包含系统和框架代码，它可以启动和停止应用、绘制 UI、控制线程计划以及向应用提供其他低级服务。|  
|![第 3 步](../profiling/media/procguid_3.png "ProcGuid_3")|二级节点的子级为用户代码方法和异步例程，它们由二级系统和框架代码进行调用或创建。|  
|![第 4 步](../profiling/media/procguid_4.png "ProcGuid_4")|方法的子节点仅包含用于父方法调用的数据。 禁用“显示外部代码”  后，应用方法只能包含 **[外部代码]** 节点。|  
  
####  <a name="BKMK_External_Code"></a> 外部代码  
 外部代码是你编写的代码执行的系统和框架组件中的函数。 外部代码包含函数，可启动和停止应用、绘制 UI、控制线程以及向应用提供其他低级别服务。 在大多数情况下，你不会对外部代码感兴趣，因此 CPU 使用率调用关系树可将用户方法的外部函数收集到一个[外部代码]节点中。  
  
 若要查看外部代码的调用路径，请从 **“筛选器视图”** 列表中选择 **“显示外部代码”** ，然后选择 **“应用”**。  
  
 ![选择“筛选器视图”，然后选择“显示外部代码”](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 请注意，许多外部代码调用链已深度嵌套，因此函数名列的宽度可能超过所有计算机监视器（最大的计算机监视器除外）的显示宽度。 发生这种情况时，函数名将显示为 […]：  
  
 ![在调用关系树中嵌套外部代码](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 使用搜索框以找到你正在查找的节点，然后使用水平滚动条以使数据在视图中显示：  
  
 ![搜索嵌套的外部代码](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a>调用关系树数据列  
  
|||  
|-|-|  
|**总 CPU (%)**|![总数据量 % 等式](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> 所选时间范围内应用的 CPU 活动百分比（函数调用和函数调用的函数使用的）。 请注意，这不同于“CPU 利用率”  时间线图，后者是将时间范围内的应用总活动量与可用的 CPU 总容量相比较。|  
|**自测 CPU (%)**|![自测 % 等式](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> 所选时间范围内应用的 CPU 活动百分比（函数调用使用，不包括函数调用的函数活动）。|  
|**总 CPU(毫秒)**|所选时间范围内函数调用以及该函数调用函数所耗用的毫秒数。|  
|**自 CPU(毫秒)**|所选时间范围内函数调用以及该函数调用函数所耗用的毫秒数。|  
|**模块**|包含函数的模块的名称或包含 [外部代码] 节点中的函数的模块数。|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a> CPU 使用率调用关系树中的异步函数  
 当编译器遇到异步方法时，它会创建一个隐藏的类来控制方法的执行。 从概念上讲，此类是状态机，其中列出了编译器生成的函数（以异步方式调用原始方法的操作），以及正确执行它们所需的回调、计划程序和迭代器。 当由父方法调用原始方法时，运行时将从父方法的执行上下文中删除该原始方法，并且在控制应用执行的系统上下文和框架代码中运行隐藏类的方法。 异步方法通常（但不总是）在一个或多个不同线程上执行。 此代码将显示在 CPU 使用率调用关系树中，作为树的顶层节点正下方的 **[外部代码]** 节点的子级。  
  
 若要在我们的示例中查看该示例，请在时间线中重新选择 `GetMaxNumberAsyncButton_Click` 段。  
  
 ![GetMaxNumberAsyncButton_Click 报告选定内容](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 **[外部代码]** 下方的前两个节点是状态机类的编译器生成的方法。 第三个节点是对原始方法的调用。 通过展开生成的方法，可显示当前进行的操作。  
  
 ![展开的 GetMaxNumberAsyncButton_Click 调用关系树](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click` 执行的内容很少；主要管理任务值列表、计算结果最大值以及显示输出。  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext` 显示用于计划和启动 48 个任务所需的活动，这些任务将包装对 `GetNumberAsync`的调用。  
  
-   `MainPage::<GetNumberAsync>b__b` 显示调用 `GetNumber`的任务的活动。
