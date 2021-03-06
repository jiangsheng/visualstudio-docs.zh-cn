---
title: "MSBuild 概念 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSBuild, concepts
ms.assetid: 083b8ba3-e4ad-45af-bb5d-3bc81d406131
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e57abdc78bc5b5844959fe2e3077688ec496df49
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-concepts"></a>MSBuild 概念
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 提供可用于控制生成平台如何生成软件的基本 XML 架构。 若要指定生成中的组件及其生成方式，请使用这四个 MSBuild 部件：属性、项、任务和目标。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[MSBuild 属性](../msbuild/msbuild-properties.md)|介绍属性和属性集合。 属性是可用于配置生成的键/值对。|  
|[项](../msbuild/msbuild-items.md)|介绍 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 文件格式背后的常规概念，以及所有这些概念之间的关系。|  
|[目标](../msbuild/msbuild-targets.md)|介绍如何按特定的顺序将任务组合到一起，并允许从命令行调用生成过程的各个部分。|  
|[任务](../msbuild/msbuild-tasks.md)|演示如何创建 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 可用于执行原子生成操作的可执行代码单元。|  
|[比较属性和项](../msbuild/comparing-properties-and-items.md)|比较 MSBuild 属性和项。 二者都用于将信息传递给任务、计算条件，以及存储可在整个项目文件中引用的值。|  
|[MSBuild 特殊字符](../msbuild/msbuild-special-characters.md)|说明如何转义 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 为在特定上下文中作特殊用途而保留的某些字符。|  
|[演练：从头开始创建 MSBuild 项目文件](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)|演示如何只使用文本编辑器以增量方式创建基本项目文件。|  
|[演练：使用 MSBuild](../msbuild/walkthrough-using-msbuild.md)|介绍 MSBuild 的构建基块，并演示如何在不关闭 Visual Studio 集成开发环境 (IDE) 的情况下编写、操作和调试 MSBuild 项目。|  
|[MSBuild 参考](../msbuild/msbuild-reference.md)|链接到包含参考信息的文档。|  
|[MSBuild](../msbuild/msbuild.md)|概述了项目文件的 XML 架构，并演示其如何控制生成软件的过程。|