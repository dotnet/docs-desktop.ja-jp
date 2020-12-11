---
title: '方法: データ オブジェクトへ複数のデータ形式を格納する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 3f8e7233e1d28fec1f7dac114b04287aa3aff49f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974873"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a><span data-ttu-id="43fb8-102">方法: データ オブジェクトへ複数のデータ形式を格納する</span><span class="sxs-lookup"><span data-stu-id="43fb8-102">How to: Store Multiple Data Formats in a Data Object</span></span>
<span data-ttu-id="43fb8-103">次の例では、<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> メソッドを使用して、複数の形式でデータ オブジェクトにデータを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="43fb8-103">The following example shows how to use the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> method to add data to a data object in multiple formats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43fb8-104">例</span><span class="sxs-lookup"><span data-stu-id="43fb8-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="43fb8-105">説明</span><span class="sxs-lookup"><span data-stu-id="43fb8-105">Description</span></span>  
  
### <a name="code"></a><span data-ttu-id="43fb8-106">コード</span><span class="sxs-lookup"><span data-stu-id="43fb8-106">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a><span data-ttu-id="43fb8-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="43fb8-107">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="43fb8-108">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="43fb8-108">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
