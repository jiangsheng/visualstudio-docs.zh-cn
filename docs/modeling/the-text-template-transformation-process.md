---
title: "文本模板转换过程 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, transformation process
ms.assetid: 80b3f0e0-49e7-4865-a1ac-dba068abe96b
caps.latest.revision: "30"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 69f0285746709bd34914362912332d46731179c9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="the-text-template-transformation-process"></a>文本模板转换过程
文本模板转换过程使用文本模板文件作为输入并生成新的文本文件，并作为输出。 例如，你可以使用文本模板生成 Visual Basic 或 C# 代码，或者可以生成 HTML 报告。  
  
 三个组件需要此过程中的一部分： 引擎、 主机和指令处理器。 该引擎控制进程;它与主机和指令处理器，从而生成输出文件进行交互。 主机提供与环境中，如定位文件和程序集的任何交互。 指令处理器添加了功能，例如从 XML 文件或数据库中读取数据。  
  
 在两个步骤执行文本模板转换过程。 首先，该引擎创建的临时类，这被称为生成的转换类。 此类包含生成的指令和控制块的代码。 在此之后，该引擎编译并执行生成的转换类以生成输出文件。  
  
## <a name="components"></a>组件数  
  
|组件|描述|可自定义 （是/否）|  
|---------------|-----------------|------------------------------|  
|引擎|引擎组件控制文本模板转换过程|不是。|  
|Host|宿主为引擎和用户环境之间的接口。 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]是文本转换过程的主机。|可以。 你可以编写自定义主机。|  
|指令处理器|指令处理器是处理指令文本模板中的类。 你可以使用指令向文本模板提供的输入源数据。|可以。 你可以编写自定义指令处理器|  
  
## <a name="the-engine"></a>引擎  
 引擎接收字符串中的主机，处理在转换过程中使用的所有文件作为模板。 引擎然后会询问主机查找任何自定义指令处理器和环境的其他方面。 然后，该引擎编译和运行生成的转换类。 引擎会返回到主机，通常将文本保存到文件生成的文本。  
  
## <a name="the-host"></a>主机  
 主机负责与转换过程，其中包括之外的环境相关的任何内容：  
  
-   查找文本和请求的引擎或指令处理器的二进制文件。 宿主可以搜索目录和全局程序集缓存，以查找程序集。 主机可以定位引擎的自定义指令处理器代码。 主机还可以查找和读取文本文件并返回字符串作为其内容。  
  
-   提供的标准程序集和该引擎用于创建生成的转换类的命名空间的列表。  
  
-   提供引擎编译和执行生成的转换类时所使用的应用程序域。 为了保护主机应用程序从模板代码中的错误情况下，将使用单独的应用程序域。  
  
-   写入生成的输出文件。  
  
-   设置生成的输出文件的默认扩展。  
  
-   处理文本模板转换错误。 例如，主机可以在用户界面中显示的错误或写入到的文件。 (在[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，错误将显示在错误消息窗口。)  
  
-   如果用户已调用一个指令，而无需提供一个值，请提供所需的参数值。 指令处理器可以指定该指令和参数的名称，并要求提供默认值，如果它有一个主机。  
  
## <a name="directives-and-directive-processors"></a>指令和指令处理器  
 指令是文本模板中的命令。 它提供了到生成过程的参数。 通常指令定义的源和类型的模型或其他输入和输出文件的文件扩展名。  
  
 指令处理器可以处理一个或多个指令。 在转换模板时，你必须已安装可以处理你的模板中的指令的指令处理器。  
  
 指令通过向生成的转换类中添加代码发挥作用。 创建生成的转换类时，可调用从一个文本模板和引擎进程在指令的所有调用指令。 已成功调用指令后，文本模板中编写的代码的其余部分可以依赖于该指令提供的功能。 例如，你可以对的以下调用`import`指令模板中：  
  
 `<#@ import namespace="System.Text" #>`  
  
 标准的指令处理器将转换到`using`生成的转换类中的语句。 然后，可以使用`StringBuilder`类中的模板代码，而不用其限定为 rest `System.Text.StringBuilder`。