---
title: '方法: ビジュアルのオフセットを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: 4787b771c7e59a8b033b9267079c068a5845a1e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983083"
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="e9125-102">方法: ビジュアルのオフセットを取得する</span><span class="sxs-lookup"><span data-stu-id="e9125-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="e9125-103">これらの例では、ビジュアル オブジェクトの親、または先祖や子孫に対する相対的なオフセット値を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e9125-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9125-104">例</span><span class="sxs-lookup"><span data-stu-id="e9125-104">Example</span></span>  
 <span data-ttu-id="e9125-105">次のマークアップの例は、<xref:System.Windows.FrameworkElement.Margin%2A> 値 4 で定義されている <xref:System.Windows.Controls.TextBlock> を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9125-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="e9125-106">次のコード例は、<xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> メソッドを使用して、<xref:System.Windows.Controls.TextBlock> のオフセットを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9125-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="e9125-107">オフセット値は、返された <xref:System.Windows.Vector> 値内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9125-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="e9125-108">オフセットでは、<xref:System.Windows.FrameworkElement.Margin%2A> 値が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="e9125-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="e9125-109">この場合、<xref:System.Windows.Vector.X%2A> は 4 で、<xref:System.Windows.Vector.Y%2A> は 4 です。</span><span class="sxs-lookup"><span data-stu-id="e9125-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="e9125-110">返されるオフセット値は、<xref:System.Windows.Media.Visual> の親に対する相対値です。</span><span class="sxs-lookup"><span data-stu-id="e9125-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="e9125-111"><xref:System.Windows.Media.Visual> の親に対して相対的ではないオフセット値を返す場合は、<xref:System.Windows.Media.Visual.TransformToAncestor%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9125-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="e9125-112">先祖に対する相対的なオフセットの取得</span><span class="sxs-lookup"><span data-stu-id="e9125-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="e9125-113">次のマークアップの例は、2 つの <xref:System.Windows.Controls.StackPanel> オブジェクト内で入れ子になっている <xref:System.Windows.Controls.TextBlock> を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9125-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="e9125-114">次の図は、マークアップの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9125-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="e9125-115">![オブジェクトのオフセット値](./media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="e9125-115">![Offset values of objects](./media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="e9125-116">2 つの StackPanels 内で入れ子になった TextBlock</span><span class="sxs-lookup"><span data-stu-id="e9125-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="e9125-117">次のコード例は、<xref:System.Windows.Media.Visual.TransformToAncestor%2A> メソッドを使用して、含まれている <xref:System.Windows.Window> に対する <xref:System.Windows.Controls.TextBlock> 相対的なオフセットを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9125-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="e9125-118">オフセット値は、返された <xref:System.Windows.Media.GeneralTransform> 値内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9125-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="e9125-119">オフセットでは、オブジェクトが含まれる <xref:System.Windows.Window> 内のすべてのオブジェクトの <xref:System.Windows.FrameworkElement.Margin%2A> 値が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="e9125-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="e9125-120">この場合、<xref:System.Windows.Vector.X%2A> は 28 (16 + 8 + 4) で、<xref:System.Windows.Vector.Y%2A> は 28 です。</span><span class="sxs-lookup"><span data-stu-id="e9125-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="e9125-121">返されるオフセット値は、<xref:System.Windows.Media.Visual> の先祖に対する相対値です。</span><span class="sxs-lookup"><span data-stu-id="e9125-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="e9125-122"><xref:System.Windows.Media.Visual> の子孫に対して相対的なオフセット値を返す場合は、<xref:System.Windows.Media.Visual.TransformToDescendant%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9125-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="e9125-123">子孫に対する相対的なオフセットの取得</span><span class="sxs-lookup"><span data-stu-id="e9125-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="e9125-124">次のマークアップの例は、<xref:System.Windows.Controls.StackPanel> オブジェクト内に含まれる <xref:System.Windows.Controls.TextBlock> を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9125-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="e9125-125">次のコード例は、<xref:System.Windows.Media.Visual.TransformToDescendant%2A> メソッドを使用して、その子 <xref:System.Windows.Controls.TextBlock> に対する <xref:System.Windows.Controls.StackPanel> の相対的なオフセットを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e9125-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="e9125-126">オフセット値は、返された <xref:System.Windows.Media.GeneralTransform> 値内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9125-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="e9125-127">オフセットでは、すべてのオブジェクトの <xref:System.Windows.FrameworkElement.Margin%2A> 値が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="e9125-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="e9125-128">この場合、<xref:System.Windows.Vector.X%2A> は -4 で、<xref:System.Windows.Vector.Y%2A> は -4 です。</span><span class="sxs-lookup"><span data-stu-id="e9125-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="e9125-129">親オブジェクトはその子オブジェクトに対する相対的な負のオフセットであるため、オフセット値は負の値になります。</span><span class="sxs-lookup"><span data-stu-id="e9125-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9125-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9125-130">See also</span></span>

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="e9125-131">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="e9125-131">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
