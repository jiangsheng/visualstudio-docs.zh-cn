---
title: "依赖项关系图︰ 指南 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: 2903bec7-a93b-46a6-aac6-994ac4f3f1a7
caps.latest.revision: 55
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fd26c504273cae739ccbeef5e406891def732985
ms.openlocfilehash: 8233d0d6ce81a0869e99f5baf45b7ef7b3fc9019
ms.lasthandoff: 02/22/2017

---
# <a name="dependency-diagrams-guidelines"></a>依赖项关系图︰ 准则
通过创建描述您的应用程序体系结构的高级别*依赖项关系图*Visual Studio 中。 请确保你的代码通过验证您的代码与依赖项关系图来保持与此设计保持一致。 还可以在生成过程中包括层验证。 请参阅[第 9 频道视频︰ 设计和验证体系结构使用依赖项关系图](http://go.microsoft.com/fwlink/?LinkID=252073)。  
  
 若要查看哪些版本的 Visual Studio 支持此功能，请参阅[体系结构和建模工具的版本支持](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。  
  
## <a name="what-is-a-dependency-diagram"></a>什么是依赖项关系图？  
 类似于传统的体系结构示意图，依赖项关系图中标识的主要组件或功能单元及其相互依赖关系和的设计。 关系图中，每个节点称为*层*，表示逻辑组的命名空间、 项目或其他项目。 您可以绘制出您的设计中存在的依赖关系。 与传统的体系结构关系图不同的是，您可以验证源代码中的实际依赖关系符合您指定的预期依赖关系。 通过在[!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]上验证常规生成的一部分，您可以确保程序代码继续符合系统的体系结构将来的更改。 请参阅[依赖项关系图︰ 参考](../modeling/layer-diagrams-reference.md)。  
  
##  <a name="a-nameupdatea-how-to-design-or-update-your-app-with-dependency-diagrams"></a><a name="Update"></a>如何用设计或更新您的应用程序依赖项关系图  
 以下步骤概述了如何使用开发过程中的依赖项关系图。 本主题中的后面几节描述了有关每个步骤的更多详细信息。 如果您正在开发新的设计，请忽略引用现有代码的步骤。  
  
> [!NOTE]
>  这些步骤按大致顺序显示。 你可能需要重叠任务、重新排序它们以符合你自己的具体情况，并在项目中的每个迭代开始时重新访问它们。  
  
1.  [创建一个依赖项关系图](#Create)整个应用程序，或其中的层。  
  
2.  [定义层以表示主要功能区域或组件](#CreateLayers)您的应用程序。 按其功能命名这些层，例如“演示文稿”或“服务”。 如果您有[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]解决方案，可以将每个图层关联的集合*项目*，如项目、 命名空间、 文件等。  
  
3.  [发现现有依赖关系](#Generate)各层之间。  
  
4.  [编辑层和依赖项](#EditArchitecture)以显示已更新所需的代码以反映设计方案。  
  
5.  [设计您的应用程序的新区域](#NewAreas)通过创建层以表示主要的体系结构块或组件，并定义依赖项以显示每个层相互使用的方式。  
  
6.  [编辑的布局和图表的外观](#EditLayout)有助于您与同事进行讨论。  
  
7.  [对照依赖项关系图验证代码](#Validate)以突出显示代码与您需要的体系结构之间的冲突。  
  
8.  [更新代码以符合新体系结构](#UpdateCode)。 以迭代方式开发和重构代码，直到此验证不再显示有冲突。  
  
9. [在生成过程中包括层验证](#BuildValidation)以确保代码继续遵循您的设计。  
  
##  <a name="a-namecreatea-create-a-dependency-diagram"></a><a name="Create"></a>创建一个依赖项关系图  
 必须在建模项目内创建一个依赖项关系图。 可以将新的依赖项关系图添加到一个现有建模项目、 创建依赖项关系图中，一个新建模项目或复制现有的依赖项关系图的同一建模项目中。  
  
> [!IMPORTANT]
>  不要添加、 拖动，或将从一个建模项目的现有依赖项关系图复制到另一个建模项目或解决方案中的另一个位置。 在这种方式中复制依赖项关系图将具有与原始关系图中，相同的引用，即使您修改该关系图。 这将阻止层验证正常操作，并可能导致出现其他问题，例如，尝试打开该关系图时元素缺失或出现其他错误。  
  
 请参阅[从您的代码创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)。  
  
##  <a name="a-namecreatelayersa-define-layers-to-represent-functional-areas-or-components"></a><a name="CreateLayers"></a>定义层以表示功能区域或组件  
 层表示的逻辑组*项目*，如项目、 代码文件、 命名空间、 类和方法。 可以从 Visual C# .NET 和 Visual Basic .NET 项目创建层，也可以通过链接文档（如 Word 文件或 PowerPoint 演示文稿）将规范或计划附加到层。 每一层显示为关系图上的一个矩形，并显示链接到它的项目数。 一个层可以包含描述更具体任务的嵌套的层。  
  
 一般原则是按其功能命名层，例如“演示文稿”或“服务”。 如果这些项目依赖关系紧密，则将它们放在同一层。 如果可以分别更新或在单独的应用程序中使用这些项目，请将它们放在不同的层中。 若要了解有关分层模式，请访问处的模式 & 和实施方案网站[http://go.microsoft.com/fwlink/?LinkId=145794](http://go.microsoft.com/fwlink/?LinkId=145794)。  
  
> [!TIP]
>  某些类型的可链接到层的项目，但不是支持对依赖项关系图的验证。 若要查看该项目是否支持验证，请打开**层资源管理器**检查**支持验证**项目链接的属性。 请参阅[发现各层之间的现有依赖关系](#Generate)。  
  
 更新不熟悉的应用程序时，你也可以创建代码图。 这些关系图可以帮助你在浏览代码时发现模式和依赖项。 使用解决方案资源管理器来浏览命名空间和类，它们通常与现有层具有很好的对应关系。 通过从解决方案资源管理器拖动到依赖项关系图为层分配这些代码项目。 然后可以使用依赖项关系图来帮助您更新代码，并使其与您的设计保持一致。  
  
 请参阅：  
  
-   [在代码中创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [使用代码图调试应用程序](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [映射解决方案中的依赖项](../modeling/map-dependencies-across-your-solutions.md)  
  
##  <a name="a-namegeneratea-discover-existing-dependencies-between-layers"></a><a name="Generate"></a>发现各层之间的现有依赖关系  
 只要与一个层关联的项目引用与另一个层关联的项目，就存在依赖关系。 例如，一个层中的某个类声明了一个拥有其他层中的某个类的变量。 您可以对它们实施反向工程来发现现有依赖关系。  
  
> [!NOTE]
>  无法为某些种类的项目对依赖关系进行反向工程处理。 例如，对于链接到文本文件的层，将不会对源自或指向该层的依赖关系进行反向工程处理。 要查看哪些项目具有可进行反向工程处理依赖项，请右击一个或多个层，然后单击**查看链接**。 在**层资源管理器**，检查**支持验证**列。 依赖项不会为其此列显示的项目实施反向工程**False**。  
  
#### <a name="to-reverse-engineer-existing-dependencies-between-layers"></a>为对层之间的现有依赖关系进行反向工程  
  
-   选择一个或多个层，用鼠标右键单击所选的层，然后单击**生成依赖项**。  
  
 通常，您会看到一些不应存在的依赖关系。 可以编辑这些依赖关系，使它们与预期的设计对齐。  
  
##  <a name="a-nameeditarchitecturea-edit-layers-and-dependencies-to-show-the-intended-design"></a><a name="EditArchitecture"></a>编辑层和依赖项以显示预期的设计  
 若要描述你计划对您的系统或计划的体系结构进行的更改，请使用以下步骤来编辑依赖项关系图。 你还可以考虑进行一些重构的更改，以提高代码的结构，然后再扩展。 请参阅[提高代码的结构](#Improving)。  
  
|**若要**|**执行这些步骤**|  
|------------|-----------------------------|  
|删除不应存在的依赖项|单击依赖项，并按**删除**。|  
|更改或限制依赖项的方向|设置其**方向**属性。|  
|创建新的依赖项|使用**依赖项**和**双向依赖项**工具。<br /><br /> 若要绘制多个依赖关系，请双击该工具。 当完成后，单击**指针**工具或按**ESC**键。|  
|指定与层关联的项目不能依赖于指定的命名空间|键入命名空间中的层**Forbidden Namespace Dependencies**属性。 使用分号 (**;**) 来分隔命名空间。|  
|指定与层关联的项目必须不属于指定的命名空间|键入命名空间中的层**Forbidden Namespaces**属性。 使用分号 (**;**) 来分隔命名空间。|  
|指定与层关联的项目必须属于某个指定的命名空间|键入命名空间中的层**Required Namespaces**属性。 使用分号 (**;**) 来分隔命名空间。|  
  
###  <a name="a-nameimprovinga-improving-the-structure-of-the-code"></a><a name="Improving"></a>提高代码的结构  
 重构更改的改进不会影响应用程序的行为，但有助于使代码在将来更易于更改和扩展。 结构良好的代码具有设计容易抽象化为依赖项关系图。  
  
 例如，如果你为代码中的每个命名空间创建图层，然后进行反向工程处理依赖关系，各层之间应该有单向依赖项的最小集。 如果您使用类或方法创建更详细的关系图作为您的层，则结果也将具有相同的特征。  
  
 如果这不是这种情况，该代码将更加难以在其生命周期更改，并且将不太适用于使用依赖项关系图进行验证。  
  
##  <a name="a-namenewareasa-design-new-areas-of-your-application"></a><a name="NewAreas"></a>设计您的应用程序的新区域  
 当你启动开发新项目或新项目中的新区域时，你可以绘制层和依赖项，以帮助你在开始开发代码之前标识主要组件。  
  
-   **显示可识别的体系结构模式**您依赖项关系图中，如有可能。 例如，描述桌面应用程序的依赖项关系图可能包括演示文稿、 域逻辑和数据存储等层。 涵盖应用程序中的单个功能的依赖项关系图可能有模型、 视图和控制器等一些层。 有关此类模式的详细信息，请参阅[模式 & 和实施方案︰ 应用程序体系结构](http://go.microsoft.com/fwlink/?LinkId=145794)。  
  
     如果您要频繁创建相似的模式，请创建一个自定义工具。 请参阅[定义一个自定义建模工具箱项](../modeling/define-a-custom-modeling-toolbox-item.md)。  
  
-   **创建代码项目的每一层**如命名空间、 类或组件。 这样，就更容易跟踪代码，并把代码项目链接到层。 当你创建每个项目时，将其链接到相应的层。  
  
-   **无需将大多数类和其他项目链接到层**因为它们归属于较大的项目，例如您已经链接到层的命名空间。  
  
-   **创建一项新功能的新关系图**。 通常情况下，将有一个或多个依赖项关系图来描述整个应用程序。 如果您正在设计应用程序的新功能，请勿添加或更改现有的关系图。 相反，创建您自己的关系图来反映代码的新部分。 新关系图中的图层可能包括演示文稿、域逻辑和新功能的数据库层。  
  
     在生成应用程序时，将同时对整体的关系图和更详细的功能关系图验证您的代码。  
  
##  <a name="a-nameeditlayouta-edit-the-layout-for-presentation-and-discussion"></a><a name="EditLayout"></a>编辑演示和讨论的布局  
 为了帮助你识别层和依赖项或与团队成员对其进行讨论，你可以按以下方式编辑关系图的外观和布局：  
  
-   更改图层的大小、 形状和位置。  
  
-   更改层的颜色和依赖项。  
  
    -   选择一个或多个层或依赖项，右键单击，然后单击**属性**。 在**属性**窗口中，编辑**颜色**属性。  
  
##  <a name="a-namevalidatea-validate-the-code-against-the-diagram"></a><a name="Validate"></a>对照关系图验证代码  
 编辑关系图之后，您可以对照代码随时手动验证关系图，也可以在每次运行本地生成或[!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]时进行自动验证。  
  
 请参阅：  
  
-   [使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)  
  
-   [在生成过程中包括层验证](#BuildValidation)  
  
##  <a name="a-nameupdatecodea-update-the-code-to-conform-to-the-new-architecture"></a><a name="UpdateCode"></a>更新代码以符合新体系结构  
 通常情况下，错误将出现第一次验证更新的依赖项关系图的代码。 这些错误可能有几个原因：  
  
-   将项目指派给了错误的层。 在这种情况下，请移动项目。  
  
-   项目（例如类）以与你的体系结构相冲突的方式使用了其他类。 在这种情况下，请重构代码以移除依赖关系。  
  
 若要解决这些错误，请更新代码，直至验证过程中不出现其他错误为止。 这通常是一个迭代过程。 有关这些错误的详细信息，请参阅[使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)。  
  
> [!NOTE]
>  在开发或重构代码时，可能会有新项目要链接到依赖项关系图。 但是，这可能不是必要的，例如，当你的层表示现有命名空间时，而且新代码只是向这些命名空间中添加更多的材料。  
  
 在开发过程中，你可能需要在验证期间禁止显示报告的某些冲突。 例如，你可能希望禁止显示你已解决或与特定情形不相关的错误。 禁止显示错误时，最好在 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] 中记录工作项。 若要执行此任务，请参阅[使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)。  
  
##  <a name="a-namebuildvalidationa-include-layer-validation-in-the-build-process"></a><a name="BuildValidation"></a>在生成过程中包括层验证  
 若要确保将来更改的代码符合依赖项关系图，包括到您的解决方案的标准生成过程的层验证。 在其他团队成员生成解决方案时，将作为生成错误报告在代码中的依赖关系和依赖项关系图之间的差异。 有关在生成过程中包括层验证的详细信息，请参阅[使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)。  
  
## <a name="see-also"></a>另请参阅  
 [依赖项关系图︰ 参考](../modeling/layer-diagrams-reference.md)   
 [在代码中创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)
