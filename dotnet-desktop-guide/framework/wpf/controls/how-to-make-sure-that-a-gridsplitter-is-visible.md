---
title: '方法: GridSplitter を表示されるようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 2085ac5cec206d8692a1267acf132688f0aa9082
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985848"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="fb1a3-102">方法: GridSplitter を表示されるようにする</span><span class="sxs-lookup"><span data-stu-id="fb1a3-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="fb1a3-103">この例では、<xref:System.Windows.Controls.Grid> 内の他のコントロールによって <xref:System.Windows.Controls.GridSplitter> コントロールが非表示にされていないことを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb1a3-104">例</span><span class="sxs-lookup"><span data-stu-id="fb1a3-104">Example</span></span>  
 <span data-ttu-id="fb1a3-105"><xref:System.Windows.Controls.Grid> コントロールの <xref:System.Windows.Controls.Panel.Children%2A> は、マークアップまたはコードで定義されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="fb1a3-106"><xref:System.Windows.Controls.GridSplitter> コントロールは、<xref:System.Windows.Controls.Panel.Children%2A> コレクション内の最後の要素として定義されていない場合、またはより高い <xref:System.Windows.Controls.Panel.ZIndexProperty> が他のコントロールに指定されている場合に、他のコントロールによって非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="fb1a3-107"><xref:System.Windows.Controls.GridSplitter> コントロールが非表示にされないようにするには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
- <span data-ttu-id="fb1a3-108"><xref:System.Windows.Controls.GridSplitter> コントロールが <xref:System.Windows.Controls.Grid> に追加された最後の <xref:System.Windows.Controls.Panel.Children%2A> であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="fb1a3-109">次の例では、<xref:System.Windows.Controls.Grid> の <xref:System.Windows.Controls.Panel.Children%2A> コレクション内の最後の要素として <xref:System.Windows.Controls.GridSplitter> が示されています。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- <span data-ttu-id="fb1a3-110"><xref:System.Windows.Controls.GridSplitter> の <xref:System.Windows.Controls.Panel.ZIndexProperty> を、非表示にされないよう、コントロールよりも高く設定します。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="fb1a3-111">次の例では、<xref:System.Windows.Controls.Button> コントロールよりも高い <xref:System.Windows.Controls.Panel.ZIndexProperty> が <xref:System.Windows.Controls.GridSplitter> コントロールに設定されています。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- <span data-ttu-id="fb1a3-112"><xref:System.Windows.Controls.GridSplitter> が表示されるようにするため、<xref:System.Windows.Controls.GridSplitter> が非表示にされないようにコントロールに余白を設定します。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="fb1a3-113">次の例では、<xref:System.Windows.Controls.GridSplitter> がオーバーレイされて非表示にされないように、コントロールに余白が設定されています。</span><span class="sxs-lookup"><span data-stu-id="fb1a3-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="fb1a3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb1a3-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="fb1a3-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="fb1a3-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
