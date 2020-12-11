---
title: '方法: ScrollViewer を持つエキスパンダーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984827"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="895b8-102">方法: ScrollViewer を持つエキスパンダーを作成する</span><span class="sxs-lookup"><span data-stu-id="895b8-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="895b8-103">この例では、画像やテキストなど、複雑なコンテンツが含まれる <xref:System.Windows.Controls.Expander> コントロールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="895b8-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="895b8-104">この例ではまた、<xref:System.Windows.Controls.Expander> のコンテンツが <xref:System.Windows.Controls.ScrollViewer> コントロールに入ります。</span><span class="sxs-lookup"><span data-stu-id="895b8-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="895b8-105">例</span><span class="sxs-lookup"><span data-stu-id="895b8-105">Example</span></span>  
 <span data-ttu-id="895b8-106"><xref:System.Windows.Controls.Expander> を作成する方法を次のコード サンプルに示します。</span><span class="sxs-lookup"><span data-stu-id="895b8-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="895b8-107">この例では、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A> を定義する目的で、画像とテキストが含まれる <xref:System.Windows.Controls.Primitives.BulletDecorator> コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="895b8-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="895b8-108"><xref:System.Windows.Controls.ScrollViewer> コントロールからは、展開したコンテンツをスクロールする手段が与えられます。</span><span class="sxs-lookup"><span data-stu-id="895b8-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="895b8-109">この例では、コンテンツではなく <xref:System.Windows.Controls.ScrollViewer> で <xref:System.Windows.FrameworkElement.Height%2A> プロパティが設定されることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="895b8-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="895b8-110"><xref:System.Windows.FrameworkElement.Height%2A> がコンテンツで設定される場合、ユーザーがコンテンツをスクロールすることが <xref:System.Windows.Controls.ScrollViewer> で許可されることはありません。</span><span class="sxs-lookup"><span data-stu-id="895b8-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="895b8-111"><xref:System.Windows.FrameworkElement.Width%2A> プロパティは <xref:System.Windows.Controls.Expander> コントロールに設定され、この設定が <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> と展開されたコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="895b8-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="895b8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="895b8-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="895b8-113">エキスパンダーの概要</span><span class="sxs-lookup"><span data-stu-id="895b8-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="895b8-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="895b8-114">How-to Topics</span></span>](expander-how-to-topics.md)
