---
title: "如何： 调整 NamedRange 控件的大小 |Microsoft 文档"
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
- controls [Office development in Visual Studio], resizing
- NamedRange control, resizing
- ranges, resizing in Excel
ms.assetid: 7d6f0b2f-be46-49b7-9f38-b4c8849683f7
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3ef581f46dd834a253e32ab169fc7d36c1c1514b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-namedrange-controls"></a>如何：调整 NamedRange 控件的大小
  将 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控件添加到 Microsoft Office Excel 文档时，可以设置该控件的大小；但是，你可能需要在以后调整其大小。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 在文档级项目中，可以在设计时或运行时调整命名范围的大小。 还可以在运行时在应用程序级 VSTO 外接程序中调整命名范围的大小。  
  
 本主题介绍了以下任务：  
  
-   [在设计时调整 NamedRange 控件的大小](#designtime)  
  
-   [在运行时，在文档级项目中调整 NamedRange 控件的大小](#runtimedoclevel)  
  
-   [在运行时，在 VSTO 外接程序项目中调整 NamedRange 控件的大小](#runtimeaddin)  
  
##  <a name="designtime"></a> Resizing NamedRange Controls at Design Time  
 可以通过在“定义名称”  对话框中重新定义其大小来调整命名范围的大小。  
  
#### <a name="to-resize-a-named-range-by-using-the-define-name-dialog-box"></a>使用“定义名称”对话框来调整命名范围的大小  
  
1.  右击 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控件。  
  
2.  在快捷菜单上单击“管理命名范围”  。  
  
     “定义名称”  对话框随即出现。  
  
3.  选择要调整大小的命名范围。  
  
4.  清除 **引用** 框。  
  
5.  选择要用来定义命名范围大小的单元格。  
  
6.  单击 **“确定”**。  
  
##  <a name="runtimedoclevel"></a> Resizing NamedRange Controls at Run Time in a Document-Level Project  
 可以通过编程的方式，使用 <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> 属性调整命名范围的大小。  
  
> [!NOTE]  
>  在“属性”  窗口中， <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> 属性标记为“只读”。  
  
#### <a name="to-resize-a-named-range-programmatically"></a>以编程方式调整命名范围大小  
  
1.  在 <xref:Microsoft.Office.Tools.Excel.NamedRange> 的单元格 **A1** 中创建一个 `Sheet1`控件。  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#4)]  
  
2.  调整命名范围的大小，使其包含单元格 **B1**。  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#5)]  
  
##  <a name="runtimeaddin"></a> Resizing NamedRange Controls at Run Time in an VSTO Add-in project  
 你可以在运行时在任何打开的工作表中调整 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控件的大小。 有关如何使用 VSTO 外接程序向工作表添加 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控件的详细信息，请参阅 [How to: Add NamedRange Controls to Worksheets](../vsto/how-to-add-namedrange-controls-to-worksheets.md)。  
  
#### <a name="to-resize-a-named-range-programmatically"></a>以编程方式调整命名范围大小  
  
1.  在 <xref:Microsoft.Office.Tools.Excel.NamedRange> 的单元格 **A1** 中创建一个 `Sheet1`控件。  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#10)]
     [!code-vb[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#10)]  
  
2.  调整命名范围的大小，使其包含单元格 **B1**。  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#11)]
     [!code-vb[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#11)]  
  
## <a name="see-also"></a>请参阅  
 [在运行时扩展 Word 文档和 Excel 工作簿在 VSTO 外接程序](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [在运行时向 Office 文档添加控件](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office 文档上的控件](../vsto/controls-on-office-documents.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [使用扩展对象实现 Excel 自动化](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange 控件](../vsto/namedrange-control.md)   
 [如何： 向工作表添加 NamedRange 控件](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [如何： 调整书签控件的大小](../vsto/how-to-resize-bookmark-controls.md)   
 [如何：调整 ListObject 控件的大小](../vsto/how-to-resize-listobject-controls.md)  
  
  