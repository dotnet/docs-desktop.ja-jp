---
title: '方法: 特定のデータ形式でデータを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981447"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="aeb32-102">方法: 特定のデータ形式でデータを取得する</span><span class="sxs-lookup"><span data-stu-id="aeb32-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="aeb32-103">次の例では、指定の形式でデータ オブジェクトからデータを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aeb32-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aeb32-104">例</span><span class="sxs-lookup"><span data-stu-id="aeb32-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aeb32-105">説明</span><span class="sxs-lookup"><span data-stu-id="aeb32-105">Description</span></span>  
 <span data-ttu-id="aeb32-106">次のコード例では、<xref:System.Windows.DataObject.GetDataPresent%28System.String%29> オーバーロードを使用し、指定のデータ形式が利用できるかどうかをまず確認します (ネイティブで利用できるか、自動変換で利用できるか)。指定の形式が利用できる場合、この例では、<xref:System.Windows.DataObject.GetData%28System.String%29> メソッドを使用することでデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="aeb32-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aeb32-107">コード</span><span class="sxs-lookup"><span data-stu-id="aeb32-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="aeb32-108">例</span><span class="sxs-lookup"><span data-stu-id="aeb32-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aeb32-109">説明</span><span class="sxs-lookup"><span data-stu-id="aeb32-109">Description</span></span>  
 <span data-ttu-id="aeb32-110">次のコード例では、<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> オーバーロードを使用し、指定のデータ形式が利用できるかどうかをまず確認します (自動変換できるデータ形式がフィルター処理される)。指定の形式が利用できる場合、この例では、<xref:System.Windows.DataObject.GetData%28System.String%29> メソッドを使用することでデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="aeb32-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aeb32-111">コード</span><span class="sxs-lookup"><span data-stu-id="aeb32-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="aeb32-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="aeb32-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="aeb32-113">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="aeb32-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
