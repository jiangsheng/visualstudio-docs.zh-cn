---
title: "SccGetCommandOptions 函数 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccGetCommandOptions
helpviewer_keywords:
- SccGetCommandOptions function
ms.assetid: bbe4aa4e-b4b0-403e-b7a0-5dd6eb24e5a9
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 86f8b896581d4238e1328bd0fe086987145c9fb5
ms.lasthandoff: 02/22/2017

---
# <a name="sccgetcommandoptions-function"></a>SccGetCommandOptions 函数
此函数会提示用户提供对于给定的命令的高级选项。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
SCCRTN SccGetCommandOptions(  
   LPVOID pvContext,  
   HWND hWnd,  
   enum SCCCOMMAND iCommand,  
   LPCMDOPTS* ppvOptions  
);  
```  
  
#### <a name="parameters"></a>参数  
 pvContext  
 [in]源控制插件上下文结构。  
  
 hWnd  
 [in]源代码管理插件可以用作所有对话框，它提供了一个父 IDE 窗口的句柄。  
  
 iCommand  
 [in]为其请求高级的选项的命令 (请参阅[命令代码](../extensibility/command-code-enumerator.md)有关可能的值)。  
  
 ppvOptions  
 [in]选项的结构 (也可以是`NULL`)。  
  
## <a name="return-value"></a>返回值  
 此函数的源代码控制插件实现应返回下列值之一︰  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|成功。|  
|SCC_I_ADV_SUPPORT|源代码管理插件支持的命令的高级的选项。|  
|SCC_I_OPERATIONCANCELED|用户取消了的源控制即插即用接**选项**对话框。|  
|SCC_E_OPTNOTSUPPORTED|源代码管理插件不支持此操作。|  
|SCC_E_ISCHECKEDOUT|无法执行此操作对当前已签出文件。|  
|SCC_E_ACCESSFAILURE|没有访问源代码管理系统，很可能是由于网络或争用问题时出现问题。 建议重试。|  
|SCC_E_NONSPECIFICERROR|非特定故障。|  
  
## <a name="remarks"></a>备注  
 IDE 与第一次调用此函数`ppvOptions` = `NULL`来判断源代码管理插件是否支持指定命令的高级的选项功能。 如果插件支持该功能为该命令，IDE 将调用此函数再次当用户请求的高级的选项 (通常作为实现**高级**在对话框中的按钮)，并提供为非 NULL 指针`ppvOptions`指向`NULL`指针。 该插件将存储在私有结构中用户指定的任何高级的选项和将指针返回到在该结构`ppvOptions`。 然后，此结构传递到需要了解它，其中包括对后续调用的所有其他源控制插件 API 函数`SccGetCommandOptions`函数。  
  
 一个例子来帮助阐明这种情况。  
  
 用户选择**获取**命令并且 IDE 显示**获取**对话框。 IDE 调用`SccGetCommandOptions`起作用`iCommand`设置为`SCC_COMMAND_GET`和`ppvOptions`设置为`NULL`。 这由源代码管理插件与问题解释，"您为此命令的任何高级的选项？" 如果该插件返回`SCC_I_ADV_SUPPORT`，则 IDE 将显示**高级**按钮在其**获取**对话框。  
  
 第一次用户单击**高级**按钮，IDE 再次调用`SccGetCommandOptions`正常工作，这次它带有一个非`NULL``ppvOptions`指向`NULL`指针。 插件显示其自身**获取选项**对话框中，将提示用户输入的信息，该将信息放入自己的结构，并将指针返回到在该结构`ppvOptions`。  
  
 如果用户单击**高级**再次在同一对话框中，IDE 调用`SccGetCommandOptions`再次而无需更改函数`ppvOptions`，因此，结构传递给插件。 这样，要重新初始化其用户以前设置的值的对话框中的插件。 该插件修改在返回之前的位置中的结构。  
  
 最后，当用户单击**确定**在 IDE 中**获取**对话框中，IDE 将调用[SccGet](../extensibility/sccget-function.md)，并传入此结构中返回`ppvOptions`，它包含高级的选项。  
  
> [!NOTE]
>  该命令`SCC_COMMAND_OPTIONS`时则 IDE 将显示使用**选项**对话框中，使用户能够设置控制集成的工作方式的首选项。 如果源代码管理插件想要提供其自己的首选项对话框中，它能够显示它从**高级**IDE 的首选项对话框中的按钮。 插件是用于获取和保存此信息; 负完全责任IDE 不使用它或对其进行修改。  
  
## <a name="see-also"></a>另请参阅  
 [源代码管理插件 API 功能](../extensibility/source-control-plug-in-api-functions.md)   
 [命令代码](../extensibility/command-code-enumerator.md)