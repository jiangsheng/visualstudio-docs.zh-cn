---
title: "无法从这些实参推断类型形参的数据类型，因为这些数据类型不会转换为同一类型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36659"
  - "bc36659"
  - "vbc36656"
  - "bc36656"
helpviewer_keywords: 
  - "BC36659"
  - "BC36656"
ms.assetid: 0aa809da-3b44-4d78-b3c5-0a148bdf7ce8
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 无法从这些实参推断类型形参的数据类型，因为这些数据类型不会转换为同一类型
无法根据这些参数推断出类型参数的数据类型，因为它们没有转换为同一类型。 显式指定数据类型可更正此错误。  
  
 当重载决策失败时发生此错误。 它以从属消息的形式发生，该消息指出已消除特定的重载候选。 此错误解释编译器无法使用类型推断功能来确定与实参兼容的类型形参的数据类型。  
  
> [!NOTE]
>  当无法指定实参时（例如，对于查询表达式中的查询运算符），显示的错误消息不包括第二个句子。  
  
 有关更多信息和示例，请参见[无法根据这些参数推断出方法“\<methodname\>”中类型形参的数据类型，因为它们没有转换为同一类型](../Topic/Data%20type\(s\)%20of%20the%20type%20parameter\(s\)%20in%20method%20'%3Cmethodname%3E'%20cannot%20be%20inferred%20from%20these%20arguments%20because%20they%20do%20not%20convert%20to%20the%20same%20type.md)。  
  
 **错误 ID：**BC36659 和 BC36656  
  
## 请参阅  
 [宽松委托转换](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [Visual Basic 中的泛型过程](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [重载决策](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)