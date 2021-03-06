---
title: "如何： 以编程方式向 Word 表中添加行和列 |Microsoft 文档"
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
- rows [Office development in Visual Studio], adding to Word tables
- tables [Office development in Visual Studio], adding rows and columns
- columns [Office development in Visual Studio], adding to Word tables
ms.assetid: 01a9b6ca-1373-4a6e-b9e6-2225a1321daf
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 56d8c3d0c578d2dc13cf65af680bc2fb804f3539
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-rows-and-columns-to-word-tables"></a>如何：以编程方式向 Word 表中添加行和列
  在 Microsoft Office Word 表中，单元格组织为行和列。 你可以使用 <xref:Microsoft.Office.Interop.Word.Rows> 对象的 <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 方法将行添加到表，并可以使用 <xref:Microsoft.Office.Interop.Word.Columns> 对象的 <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 方法添加列。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customization-examples"></a>文档级自定义项示例  
 可以在文档级自定义项中使用下列代码示例。 若要使用这些示例，请从项目中的 `ThisDocument` 类运行它们。 这些示例假定与你的自定义相关联的文档已具有至少一个表。  
  
> [!IMPORTANT]  
>  此代码仅在使用下列任意项目模板创建的项目中运行：  
>   
>  -   Word 2013 文档  
> -   Word 2013 模板  
> -   Word 2010 文档  
> -   Word 2010 模板  
>   
>  如果你想要在任何其他类型的项目中执行此任务，则必须添加对引用**Microsoft.Office.Interop.Word**程序集，然后必须使用该程序集的类向表添加行和列。 有关详细信息，请参阅[如何： 应用程序通过主互操作程序集面向 Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)和[Word 2010 主互操作程序集引用](http://go.microsoft.com/fwlink/?LinkId=189588)。  
  
#### <a name="to-add-a-row-to-a-table"></a>向表中添加行  
  
1.  使用 <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 方法向表中添加一行。  
  
     [!code-vb[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>向表中添加列  
  
1.  使用 <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 方法，然后使用 <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> 方法使所有列具有相同的宽度。  
  
     [!code-vb[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#96)]  
  
## <a name="vsto-add-in-examples"></a>VSTO 外接程序示例  
 可以在 VSTO 外接程序中使用下列代码示例。 若要使用这些示例，请从项目中的 `ThisAddIn` 类运行它们。 这些示例假定活动文档已经具有至少一个表。  
  
> [!IMPORTANT]  
>  此代码仅在你使用 Word VSTO 外接程序模板创建的项目中运行。  
>   
>  如果你想要在任何其他类型的项目中执行此任务，则必须添加对引用**Microsoft.Office.Interop.Word**程序集，然后必须使用该程序集的类向表添加行和列。 有关详细信息，请参阅[如何： 应用程序通过主互操作程序集面向 Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)和[Word 2010 主互操作程序集引用](http://go.microsoft.com/fwlink/?LinkId=189588)。  
  
#### <a name="to-add-a-row-to-a-table"></a>向表中添加行  
  
1.  使用 <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 方法向表中添加一行。  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>向表中添加列  
  
1.  使用 <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 方法，然后使用 <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> 方法使所有列具有相同的宽度。  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#96)]  
  
## <a name="see-also"></a>请参阅  
 [如何： 以编程方式创建 Word 表](../vsto/how-to-programmatically-create-word-tables.md)   
 [如何： 以编程方式添加文本和格式向 Word 表中的单元格](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [如何：以编程方式用文档属性填充 Word 表格](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  