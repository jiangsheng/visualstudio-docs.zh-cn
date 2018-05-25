---
title: 使用探查器检测方法通过命令行收集 ASP.NET Web 应用程序的详细计时数据 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,instrumentation method
- instrumentation profiling method
ms.assetid: 29f2fc55-aaf7-4e18-a672-8815455fba73
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 07789eba81dbe0cce46e5cf1a14decff92a6892f
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line"></a>从命令行使用探查器检测方法收集 ASP.NET Web 应用程序的详细计时数据
本部分介绍通过 VSPerfCmd 命令行工具和检测方法来收集 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web 应用程序的详细性能数据的步骤和选项。  
  
> [!NOTE]
>  使用 VSPerfCmd 工具可完全访问分析工具功能，包括暂停和继续分析，以及从处理器和 Windows 性能计数器收集其他数据。 如果不需要此功能，也可以使用 VSPerfASPNETCmd 命令行工具。 与 [VSPerfCmd](../profiling/vsperfcmd.md) 命令行工具相比，无需设置任何环境变量，也无需重启计算机。 有关详细信息，请参阅[使用 VSPerfASPNETCmd 进行快速网站分析](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)。  
  
## <a name="common-tasks"></a>常规任务  
  
|任务|相关内容|  
|----------|---------------------|  
|**分析静态编译的二进制文件**|-   [如何：检测静态编译的 ASP.NET 应用程序并收集详细计时数据](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)|  
|**分析动态编译的二进制文件**|-   [如何：检测动态编译的 ASP.NET 应用程序并收集详细计时数据](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)|  
  
## <a name="related-tasks"></a>相关任务  
  
### <a name="profiling-aspnet-web-applications"></a>分析 ASP.NET Web 应用程序  
  
|任务|相关内容|  
|----------|---------------------|  
|**使用采样方法进行分析**|-   [使用采样法收集应用程序统计信息](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**分析内存分配和垃圾回收**|-   [收集内存数据](../profiling/collecting-memory-data-from-an-aspnet-web-application.md)|  
|**分析资源争用和线程活动**|-   [收集并发数据](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="profiling-by-using-the-instrumentation-method"></a>使用检测方法进行分析  
  
|任务|相关内容|  
|----------|---------------------|  
|**分析独立（客户端）应用程序**|-   [使用检测收集详细计时数据](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md)|  
|**分析服务**|-   [使用检测收集详细计时数据](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
  
### <a name="analyzing-instrumentation-data-views-and-reports"></a>分析检测数据视图和报告  
 [检测方法数据视图](../profiling/instrumentation-method-data-views.md)