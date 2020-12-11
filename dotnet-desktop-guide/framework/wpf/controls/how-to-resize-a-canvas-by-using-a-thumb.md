---
title: '方法: つまみを使用したキャンバスのサイズ変更'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983584"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="9fbb4-102">方法: つまみを使用したキャンバスのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="9fbb4-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="9fbb4-103">この例は、<xref:System.Windows.Controls.Primitives.Thumb> コントロールを使用して <xref:System.Windows.Controls.Canvas> コントロールのサイズを変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fbb4-104">例</span><span class="sxs-lookup"><span data-stu-id="9fbb4-104">Example</span></span>  
 <span data-ttu-id="9fbb4-105"><xref:System.Windows.Controls.Primitives.Thumb> コントロールには、<xref:System.Windows.Controls.Primitives.Thumb> の <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>、および <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> イベントを監視することにより、コントロールの移動またはサイズ変更に使用できるドラッグ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="9fbb4-106">ユーザーがドラッグ操作を始めるには、マウス ポインターが <xref:System.Windows.Controls.Primitives.Thumb> コントロールに置かれているときに、左マウス ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="9fbb4-107">マウスの左ボタンが押されている間は、ドラッグ操作が続行されます。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="9fbb4-108">ドラッグ操作中に、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta> が複数回発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="9fbb4-109">それが発生するたびに、<xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> クラスからはマウス位置の変化に対応した位置の変化が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="9fbb4-110">ユーザーがマウスの左ボタンを放すと、ドラッグ操作は終了します。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="9fbb4-111">ドラッグ操作からは、新しい座標のみが提供されます。<xref:System.Windows.Controls.Primitives.Thumb> の位置が自動的に変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="9fbb4-112">次の例は、<xref:System.Windows.Controls.Canvas> コントロールの子要素である <xref:System.Windows.Controls.Primitives.Thumb> コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="9fbb4-113"><xref:System.Windows.Controls.Primitives.Thumb.DragDelta> イベントのイベント ハンドラーには、<xref:System.Windows.Controls.Primitives.Thumb> を移動して <xref:System.Windows.Controls.Canvas> のサイズを変更するロジックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="9fbb4-114"><xref:System.Windows.Controls.Primitives.Thumb.DragStarted> および <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> イベントのイベント ハンドラーを使用すると、ドラッグ操作中に <xref:System.Windows.Controls.Primitives.Thumb> の色を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="9fbb4-115">次の例では、<xref:System.Windows.Controls.Primitives.Thumb> を定義します。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="9fbb4-116">マウスの動きに応じて <xref:System.Windows.Controls.Primitives.Thumb> を移動し、<xref:System.Windows.Controls.Canvas> のサイズを変更する <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> イベント ハンドラーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="9fbb4-117"><xref:System.Windows.Controls.Primitives.Thumb.DragStarted> イベント ハンドラーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="9fbb4-118"><xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> イベント ハンドラーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="9fbb4-119">サンプル全体については、[Thumb のドラッグ機能のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbb4-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbb4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fbb4-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
