---
title: '方法: データ オブジェクト内のデータ形式の一覧を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984892"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="007f0-102">方法: データ オブジェクト内のデータ形式の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="007f0-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="007f0-103">次の例では、<xref:System.Windows.DataObject.GetFormats%2A> メソッドのオーバーロードを使用して、データ オブジェクトで使用できる各データ形式を示す文字列の配列を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="007f0-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="007f0-104">例</span><span class="sxs-lookup"><span data-stu-id="007f0-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="007f0-105">説明</span><span class="sxs-lookup"><span data-stu-id="007f0-105">Description</span></span>  
 <span data-ttu-id="007f0-106">次のコード例では、<xref:System.Windows.DataObject.GetFormats%2A> のオーバーロードを使用して、データ オブジェクトで使用できるすべてのデータ形式 (ネイティブと自動変換の両方) を示す文字列の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="007f0-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="007f0-107">コード</span><span class="sxs-lookup"><span data-stu-id="007f0-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="007f0-108">例</span><span class="sxs-lookup"><span data-stu-id="007f0-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="007f0-109">説明</span><span class="sxs-lookup"><span data-stu-id="007f0-109">Description</span></span>  
 <span data-ttu-id="007f0-110">次のコード例では、<xref:System.Windows.DataObject.GetFormats%2A> のオーバーロードを使用して、データ オブジェクトで使用できるデータ形式のみ (自動変換可能なデータ形式はフィルター処理済み) を示す文字列の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="007f0-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="007f0-111">コード</span><span class="sxs-lookup"><span data-stu-id="007f0-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="007f0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="007f0-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="007f0-113">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="007f0-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
