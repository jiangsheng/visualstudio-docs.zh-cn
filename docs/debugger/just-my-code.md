---
title: "仅我的代码 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 0f0df097-bbaf-46ad-9ad1-ef5f40435079
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 仅我的代码
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

使用.NET Framework 语言的开发人员熟悉“仅我的代码”调试器功能，该功能会逐过程执行系统、框架和其他非用户调用，并在调用堆栈窗口中折叠这些调用。  “仅我的代码”已扩展到 C\+\+ 和 JavaScript 语言。  本主题介绍在 .NET Framework、本机 C\+\+ 和 JavaScript 项目中使用“仅我的代码”的具体信息。  
  
##  <a name="BKMK_Contents"></a> 内容  
 [启用或禁用“仅我的代码”](#BKMK_Enable_or_disable_Just_My_Code)  
  
 [.NET framework“仅我的代码”](#BKMK__NET_Framework_Just_My_Code)  
  
 [C++“仅我的代码”](#BKMK_C___Just_My_Code)  
  
 [JavaScript“仅我的代码”](#BKMK_JavaScript_Just_My_Code)  
  
##  <a name="BKMK_Enable_or_disable_Just_My_Code"></a> 启用或禁用“仅我的代码”  
 若要启用或禁用“仅我的代码”，请在**“调试”**菜单上选择**“选项和设置”**。  在**“调试”**\/**“常规”**节点中，选择或清除**“启用‘仅我的代码’”**。  
  
 ![“选项”对话框中的“启用‘仅我的代码’”](../debugger/media/dbg_justmycode_options.png "DBG\_JustMyCode\_Options")  
  
> [!NOTE]
>  **“启用‘仅我的代码’”**设置是全局设置，会应用于所有语言中的所有 Visual Studio 项目。  
  
###  <a name="BKMK_Override_call_stack_filtering"></a> 重写调用堆栈筛选  
 在调用堆栈显示中（如“调用堆栈”和“任务”窗口），“仅我的代码”会将非用户代码折叠为带有标签 `[External Code]` 的带批注帧。  若要查看折叠的帧，请在调用堆栈显示的上下文菜单上选择**“显示外部代码”**。  
  
> [!NOTE]
>  **“显示外部代码”**设置会保存到当前用户的探查器。  它会应用于所有语言中由用户打开的所有项目。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents)  
  
##  <a name="BKMK__NET_Framework_Just_My_Code"></a> .NET framework“仅我的代码”  
 [用户和非用户代码](#BKMK_NET_User_and_non_user_code) **&#124;** [单步执行行为](#BKMK_NET_Stepping_behavior) **&#124;** [断点行为](#BKMK_NET_Breakpoint_behavior) **&#124;** [异常行为](#BKMK_NET_Exception_behavior)  
  
###  <a name="BKMK_NET_User_and_non_user_code"></a> 用户和非用户代码  
 为了区分用户代码与非用户代码，“仅我的代码”会查看打开的项目、符号 \(.pdb\) 文件和程序优化。  
  
1.  如果某个二进制文件是从打开的 Visual Studio 项目中生成的，则始终将它视为用户代码。  
  
2.  当二进制文件进行了优化时或当 .pdb 文件不可用时，调试器会将代码视为非用户代码。  
  
 还有三个特性会影响调试器视为“我的代码”的内容：  
  
-   <xref:System.Diagnostics.DebuggerNonUserCodeAttribute> 告知调试器应用它的代码不是“我的代码”。  
  
-   <xref:System.Diagnostics.DebuggerHiddenAttribute> 对调试器隐藏代码，即使“仅我的代码”关闭；  
  
-   <xref:System.Diagnostics.DebuggerStepThroughAttribute> 告知调试器逐句通过其所应用的代码，而不是单步执行代码。  
  
 将所有其他代码都视为用户代码。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [.NET framework“仅我的代码”](#BKMK__NET_Framework_Just_My_Code)  
  
###  <a name="BKMK_NET_Stepping_behavior"></a> 单步执行行为  
 **“单步执行”**（键盘快捷键：F11）非用户代码时，调试器会逐过程执行代码到下一个用户语句。  **“跳出”**（键盘： Shift \+ F11）时，调试器会运行到下一行用户代码。  如果未遇到用户代码，则执行会继续，直到应用退出、命中断点或发生异常。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [.NET framework“仅我的代码”](#BKMK__NET_Framework_Just_My_Code)  
  
###  <a name="BKMK_NET_Breakpoint_behavior"></a> 断点行为  
 启用“仅我的代码”后，可以选择**“全部中断”**（键盘：Ctrl \+ Alt \+ Break），在不显示用户代码的位置处停止执行。  发生这种情况时，会显示“无源”窗口。  如果随后选择“单步执行”命令，则调试器会到达下一行用户代码。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [.NET framework“仅我的代码”](#BKMK__NET_Framework_Just_My_Code)  
  
###  <a name="BKMK_NET_Exception_behavior"></a> 异常行为  
 如果在非用户代码中出现未经处理的异常，则调试器会在用户代码中生成异常的行上中断。  
  
 如果针对异常启用了第一机会异常，则以绿色突出显示用户代码行。  调用堆栈会显示标签为**“\[外部代码\]”**的带批注帧。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [.NET framework“仅我的代码”](#BKMK__NET_Framework_Just_My_Code)  
  
##  <a name="BKMK_C___Just_My_Code"></a> C\+\+“仅我的代码”  
 [用户和非用户代码](#BKMK_CPP_User_and_non_user_code) **&#124;** [单步执行行为](#BKMK_CPP_Stepping_behavior) **&#124;** [异常行为](#BKMK_CPP_Exception_behavior) **&#124;** [自定义单步执行行为](#BKMK_CPP_Customize_stepping_behavior) **&#124;** [自定义调用堆栈行为](#BKMK_CPP_Customize_call_stack_behavior)  
  
###  <a name="BKMK_CPP_User_and_non_user_code"></a> 用户和非用户代码  
 C\+\+“仅我的代码”与 .NET Framework 和 JavaScript“仅我的代码”不同，因为单步执行行为独立于调用堆栈行为。  
  
 **调用堆栈**  
  
 默认情况下，调试器会将以下这些函数视为调用堆栈窗口中的非用户代码：  
  
-   在其符号文件中去除了源信息的函数。  
  
-   符号文件指示没有对应于堆栈帧的源文件的函数。  
  
-   `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` 文件夹的 `*.natjmc` 文件中指定的函数。  
  
 **单步执行**  
  
 默认情况下，仅将 `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` 文件夹的 `*.natstepfilter` 文件中指定的函数视为非用户代码。  
  
 可以在 `%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers` 中创建自己的 `.natstepfilter` 和 `.natjmc` 以自定义单步执行和调用堆栈窗口行为。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [C++“仅我的代码”](#BKMK_C___Just_My_Code)  
  
###  <a name="BKMK_CPP_Stepping_behavior"></a> 单步执行行为  
 从用户代码**“单步执行”**（键盘快捷键：F11）非用户代码时，调试器会逐过程执行代码到下一行用户代码。  **“跳出”**（键盘： Shift \+ F11）时，调试器会运行到下一行用户代码。  如果未遇到用户代码，则执行会继续，直到应用退出、命中断点或发生异常。  
  
 如果调试器在非用户代码中中断（例如，如果“全部中断”命令在非用户代码中停止），则单步执行会继续在非用户代码中进行。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [C++“仅我的代码”](#BKMK_C___Just_My_Code)  
  
###  <a name="BKMK_CPP_Exception_behavior"></a> 异常行为  
 当调试器遇到异常时，它会异常处停止，而不考虑是处于用户还是非用户代码中。  会忽略**“异常”**对话框中的**“用户未处理的”**选项。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [C++“仅我的代码”](#BKMK_C___Just_My_Code)  
  
###  <a name="BKMK_CPP_Customize_stepping_behavior"></a> 自定义单步执行行为  
 可以通过在 `*.natstepfilter` 文件中将函数列为非用户代码来指定要逐过程执行的函数。  
  
-   若要为 Visual Studio 计算机的所有用户指定非用户代码，请将 .  natstepfilter 文件添加到 `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` 文件夹。  
  
-   若要为单独用户指定非用户代码，请将 .  natstepfilter 文件添加到 `%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers` 文件夹。  
  
 .  natstepfilter 文件是使用以下语法的 xml 文件：  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<StepFilter xmlns="http://schemas.microsoft.com/vstudio/debugger/natstepfilter/2010">  
    <Function>  
        <Name>FunctionSpec</Name>  
        <Action>StepAction</Action>  
    </Function>  
    <Function>  
        <Name>FunctionSpec</Name>  
        <Module>ModuleSpec</Module>  
        <Action>StepAction</Action>  
    </Function>  
</StepFilter>  
  
```  
  
|元素|描述|  
|--------|--------|  
|函数|必需。  将一个或多个函数指定为非用户函数。|  
|`Name`|必需。  ECMA\-262 格式的正则表达式，指定要匹配的完整函数名。  例如:<br /><br /> `<Name>MyNS::MyClass.*</Name>`<br /><br /> 告知调试器将 `MyNS::MyClass` 中的所有方法都视为非用户代码。  匹配区分大小写。|  
|`Module`|可选。  ECMA\-262 格式的正则表达式，指定包含函数的模块的完整路径。  匹配不区分大小写。|  
|`Action`|必需。  以下区分大小写的值之一：<br /><br /> -   `NoStepInto`  – 告知调试器逐过程执行匹配的函数。<br />-   `StepInto`  – 告知调试器单步执行匹配的函数，为匹配的函数重写任何其他 `NoStepInto`。|  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [C++“仅我的代码”](#BKMK_C___Just_My_Code)  
  
###  <a name="BKMK_CPP_Customize_call_stack_behavior"></a> 自定义调用堆栈行为  
 可以通过在 `*.natjmc` 文件中指定模块、源文件和函数，将它们指定视为调用堆栈中的非用户代码。  
  
-   若要为 Visual Studio 计算机的所有用户指定非用户代码，请将 .  natjmc 文件添加到 `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` 文件夹。  
  
-   若要为单独用户指定非用户代码，请将 .  natjmc 文件添加到 `%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers` 文件夹。  
  
 .  natjmc 文件是使用以下语法的 xml 文件：  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<NonUserCode xmlns="http://schemas.microsoft.com/vstudio/debugger/jmc/2015">  
  
  <!-- Modules -->  
  <Module Name="ModuleSpec" />  
  <Module Name="ModuleSpec" Company="CompanyName" />  
  
  <!-- Files -->  
  <File Name="FileSpec"/>  
  
  <!-- Functions -->  
  <Function Name="FunctionSpec" />  
  <Function Name="FunctionSpec" Module ="ModuleSpec" />  
  <Function Name="FunctionSpec" Module ="ModuleSpec" ExceptionImplementation="true" />  
  
</NonUserCode>  
  
```  
  
 **模块元素特性**  
  
|特性|描述|  
|--------|--------|  
|`Name`|必需。  模块的完整路径。  可以使用 Windows 通配符 `?`（零个或一个字符）和 `*`（零个或多个字符）。  例如，<br /><br /> `<Module Name=”?:\3rdParty\UtilLibs\*” />`<br /><br /> 告知调试器将任何驱动器上的 `\3rdParty\UtilLibs` 中的所有模块都视为外部代码。|  
|`Company`|可选。  发布在可执行文件中嵌入的模块的公司的名称。  可以使用此特性消除模块歧义。|  
  
 **文件元素特性**  
  
|特性|描述|  
|--------|--------|  
|`Name`|必需。  要视为外部代码的源文件的完整路径。  可以在指定路径时使用 Windows 通配符 `?` 和 `*`。|  
  
 **函数元素特性**  
  
|特性|描述|  
|--------|--------|  
|`Name`|必需。  要视为外部代码的函数的完全限定的名称。|  
|`Module`|可选。  包含函数的模块的名称或完整路径。  可以使用此特性区分具有相同名称的函数。|  
|`ExceptionImplementation`|设置为 `true` 时，调用堆栈显示的是引发异常的函数，而不是此函数。|  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [C++“仅我的代码”](#BKMK_C___Just_My_Code)  
  
##  <a name="BKMK_JavaScript_Just_My_Code"></a> JavaScript“仅我的代码”  
 [用户和非用户代码](#BKMK_JS_User_and_non_user_code) **&#124;** [单步执行行为](#BKMK_JS_Stepping_behavior) **&#124;** [断点行为](#BKMK_JS_Breakpoint_behavior) **&#124;** [异常行为](#BKMK_JS_Exception_behavior) **&#124;** [自定义“仅我的代码”](#BKMK_JS_Customize_Just_My_Code)  
  
###  <a name="BKMK_JS_User_and_non_user_code"></a> 用户和非用户代码  
 **代码分类**  
  
 JavaScript“仅我的代码”控件通过采用以下分类之一对代码进行分类，来控制单步执行和调用堆栈显示：  
  
|||  
|-|-|  
|**MyCode**|你拥有或控制的用户代码。|  
|**LibraryCode**|库中由你定期使用以及应用程序为正常运行而依赖的非用户代码（例如 WinJS 或 jQuery）。|  
|**UnrelatedCode**|可以在应用程序中运行，但不由你拥有并且应用程序并不直接依赖它才能正常运行的非用户代码（例如，可以显示广告的广告 SDK）。  在 Windows 应用商店项目中，从 HTTP 或 HTTPS URI 加载到应用中的任何代码也被视为 UnrelatedCode。|  
  
 JavaScript 调试器会自动对这些类型的代码进行分类：  
  
-   通过将字符串传递给主机提供的 `eval` 函数来执行的脚本分类为 **MyCode**。  
  
-   通过将字符串传递给 `Function` 构造函数来执行的脚本分类为 **LibraryCode**。  
  
-   包含在框架引用（如 WinJS 或 Azure SDK）中的脚本分类为 **LibraryCode**。  
  
-   通过将字符串传递给 `setTimeout`、`setImmediate` 或 `setInterval` 函数来执行的脚本分类为 **UnrelatedCode**。  
  
-   `%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json` 为所有 Visual Studio JavaScript 项目指定其他用户和非用户代码。  
  
 可以通过将一个名为 `mycode.json` 的 .json 文件添加到项目的根文件夹，来修改默认分类以及对特定文件和 url 进行分类。  
  
 所有其他代码都分类为 **MyCode**。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [JavaScript“仅我的代码”](#BKMK_JavaScript_Just_My_Code)  
  
###  <a name="BKMK_JS_Stepping_behavior"></a> 单步执行行为  
  
-   如果函数不是用户 \(**MyCode**\) 代码，则**“单步执行”**（键盘快捷键：F11）的行为方式会如同**“逐过程”**（键盘：F10）。  
  
-   如果某个单步执行在非用户（**LibraryCode** 或 **UnrelatedCode**）代码中开始，则单步执行的行为方式会暂时如同未启用“仅我的代码”。  单步执行返回到用户代码中时，“仅我的代码”单步执行会立即重新启用。  
  
-   用户代码中的单步执行导致保留当前执行上下文（如对事件处理程序的最后一行进行单步执行）时，调试器会在执行的下一行用户代码处停止。  例如，如果某个回调在 **LibraryCode** 代码中执行，则调试器会继续，直到执行下一行用户代码。  
  
-   **跳出**（键盘：Shift \+ F11）会在下一行用户代码上停止。  如果未遇到用户代码，则执行会继续，直到应用退出、命中断点或发生异常。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [JavaScript“仅我的代码”](#BKMK_JavaScript_Just_My_Code)  
  
###  <a name="BKMK_JS_Breakpoint_behavior"></a> 断点行为  
  
-   在任何代码中设置的断点都始终会命中（无论该代码如何分类）。  
  
-   如果在以下内容中遇到 `debugger` 关键字：  
  
    -   **LibraryCode** 代码，调试器始终中断。  
  
    -   **UnrelatedCode** 代码，调试器不会停止。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [JavaScript“仅我的代码”](#BKMK_JavaScript_Just_My_Code)  
  
###  <a name="BKMK_JS_Exception_behavior"></a> 异常行为  
 如果在以下内容中出现未经处理的异常：  
  
-   **MyCode** 或 **LibraryCode** 代码，调试器始终中断。  
  
-   **UnrelatedCode** 代码，并且 **MyCode** 或 **LibraryCode** 代码位于调用堆栈上，调试器中断。  
  
 如果在“异常”对话框中针对异常启用了第一机会异常，并且在 **LibraryCode** 或 **UnrelatedCode** 代码中引发异常：  
  
-   如果异常经过了处理，则调试器不会中断。  
  
-   如果异常未经过处理，则调试器中断。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [JavaScript“仅我的代码”](#BKMK_JavaScript_Just_My_Code)  
  
###  <a name="BKMK_JS_Customize_Just_My_Code"></a> 自定义“仅我的代码”  
 若要针对单个 Visual Studio 项目对用户和非用户代码进行分类，请将一个名为 `mycode.json` 的 .json 文件添加到该项目的根文件夹。  
  
 按以下顺序执行分类：  
  
1.  默认分类  
  
2.  `%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json` 文件中的分类  
  
3.  当前项目的 `mycode. json` 文件中的分类。  
  
 每个分类步骤都会重写前面的步骤。  .json 文件无需列出所有键\/值对，**MyCode**、**Libraries** 和 **Unrelated** 值可以是空数组。  
  
 “我的代码”.json 文件使用以下语法：  
  
```json  
{  
    "Eval" : "Classification",  
    "Function" : "Classification",  
    "ScriptBlock" : "Classification",  
    "MyCode" : [  
        "UrlOrFileSpec”,  
        . . .  
        "UrlOrFileSpec”  
    ],  
    "Libraries" : [  
        "UrlOrFileSpec”,  
        . .  
        "UrlOrFileSpec”  
    ],  
    "Unrelated" : [  
        "UrlOrFileSpec”,  
        . . .  
        "UrlOrFileSpec”  
    ]  
}  
  
```  
  
 **Eval、Function 和 ScriptBlock**  
  
 **Eval**、**Function** 和 **ScriptBlock** 键\/值对确定如何对动态生成的代码进行分类。  
  
|||  
|-|-|  
|**Eval**|通过将字符串传递给主机提供的 `eval` 函数来执行的脚本。  默认情况下，Eval 脚本分类为 **MyCode**。|  
|**函数**|通过将字符串传递给 `Function` 构造函数来执行的脚本。  默认情况下，Function 脚本分类为 **LibraryCode**。|  
|**ScriptBlock**|通过将字符串传递给 `setTimeout`、`setImmediate` 或 `setInterval` 函数来执行的脚本。  默认情况下，ScriptBlock 脚本分类为 **UnrelatedCode**。|  
  
 可以将值更改为以下关键字之一：  
  
-   `MyCode`  将脚本分类为 **MyCode**。  
  
-   `Library`  将脚本分类为 **LibraryCode**。  
  
-   `Unrelated`  将脚本分类为 **UnrelatedCode**。  
  
 **MyCode、Libraries 和 Unrelated**  
  
 **MyCode**、**Libraries**和 **Unrelated** 键\/值对指定要包含在分类中的 url 或文件：  
  
|||  
|-|-|  
|**MyCode**|分类为 **MyCode** 的 url 或文件的数组。|  
|**库**|分类为 **LibraryCode** 的 url 或文件的数组。|  
|**Unrelated**|分类为 **UnrelatedCode** 的 url 或文件的数组。|  
  
 url 或文件字符串可以包含一个或多个 `*` 字符，这些字符匹配零个或多个字符。  `*` 是正则表达式 `.*` 的等效项。  
  
 ![返回页首](../debugger/media/pcs_backtotop.png "PCS\_BackToTop") [内容](#BKMK_Contents) **&#124;** [JavaScript“仅我的代码”](#BKMK_JavaScript_Just_My_Code)