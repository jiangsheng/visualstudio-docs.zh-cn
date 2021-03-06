---
title: "如何： 以编程方式关闭工作簿 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
ms.assetid: 50709caf-2ad8-4843-987c-9a34c8c1e4fe
caps.latest.revision: "52"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1cb28dc5b9df265178f26a0573ffe3eb5f5043d5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-close-workbooks"></a>如何：以编程方式关闭工作簿
  你可以关闭活动工作簿，也可以指定关闭某个工作簿。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="closing-the-active-workbook"></a>关闭活动工作簿  
 关闭活动工作薄有两个过程：一个用于文档级自定义项；另一个用于 VSTO 外接程序。  
  
#### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>若要关闭文档级自定义项的活动工作簿  
  
1.  调用 <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> 方法来关闭与自定义项关联的工作簿。 若要使用下面的代码示例，请在 Excel 文档级项目的 `Sheet1` 类中运行。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]  
  
#### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>若要关闭 VSTO 外接程序中的活动工作簿  
  
1.  调用 <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> 方法来关闭活动工作簿。 若要使用下面的代码示例，请在 Excel 的 VSTO 外接程序项目内的 `ThisAddIn` 类中运行它。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="closing-a-workbook-that-you-specify-by-name"></a>关闭按名称指定的工作簿  
 关闭按名称指定的工作簿的方法与关闭 VSTO 外接程序和文档级自定义项的方法相同。  
  
#### <a name="to-close-a-workbook-that-you-specify-by-name"></a>若要关闭按名称指定的工作薄  
  
1.  将工作薄名称作为自变量指定到 <xref:Microsoft.Office.Interop.Excel.Workbooks> 集合。 下面的代码示例假定名为 **NewWorkbook** 工作簿在 Excel 中打开。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [如何： 以编程方式保存工作簿](../vsto/how-to-programmatically-save-workbooks.md)   
 [如何： 以编程方式打开工作簿](../vsto/how-to-programmatically-open-workbooks.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)   
 [主机项和主机控件概述](../vsto/host-items-and-host-controls-overview.md)  
  
  