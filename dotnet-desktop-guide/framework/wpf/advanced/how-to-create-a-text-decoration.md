---
title: '方法: 文字の装飾を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984619"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="cb7ca-102">方法: 文字の装飾を作成する</span><span class="sxs-lookup"><span data-stu-id="cb7ca-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="cb7ca-103"><xref:System.Windows.TextDecoration> オブジェクトは、テキストに追加できるビジュアルな装飾です。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="cb7ca-104">文字の装飾には、下線、ベースライン、取り消し線、上線の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="cb7ca-105">次の例では、テキストに対する相対的なテキスト装飾の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![テキスト装飾の種類の図](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="cb7ca-107">テキストにテキスト装飾を追加するには、<xref:System.Windows.TextDecoration> オブジェクトを作成して、そのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="cb7ca-108">テキスト装飾を表示する場所 (下線など) を指定するには、<xref:System.Windows.TextDecoration.Location%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="cb7ca-109">塗りつぶしやグラデーションの色など、テキスト装飾の外観を指定するには、<xref:System.Windows.TextDecoration.Pen%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="cb7ca-110"><xref:System.Windows.TextDecoration.Pen%2A> プロパティの値を指定しない場合、修飾は既定で、テキストと同じ色になります。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="cb7ca-111"><xref:System.Windows.TextDecoration> オブジェクトを定義したら、それを対象のテキスト オブジェクトの <xref:System.Windows.TextDecorations> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="cb7ca-112">次の例では、線状グラデーション ブラシと破線ペンのスタイルに設定されたテキスト装飾を示します。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![線形グラデーション下線を使用したテキスト装飾](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="cb7ca-114"><xref:System.Windows.Documents.Hyperlink> オブジェクトは、インライン レベルのフロー コンテンツ要素であり、フロー コンテンツ内のハイパーリンクをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="cb7ca-115">既定では、<xref:System.Windows.Documents.Hyperlink> では下線を表示するために <xref:System.Windows.TextDecoration> オブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="cb7ca-116"><xref:System.Windows.TextDecoration> オブジェクトをインスタンス化するときは大きな負荷がかかる場合があり、<xref:System.Windows.Documents.Hyperlink> オブジェクトの数が多い場合は特にそうです。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="cb7ca-117"><xref:System.Windows.Documents.Hyperlink> 要素を広範に使用する場合は、<xref:System.Windows.ContentElement.MouseEnter> イベントなどのイベントをトリガーするときにのみ下線を表示することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="cb7ca-118">次の例では、"My MSN" のリンクに対する下線は動的であり、<xref:System.Windows.ContentElement.MouseEnter> イベントがトリガーされたときにだけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![TextDecorations を表示するハイパーリンク](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="cb7ca-120">詳細については、「[方法: ハイパーリンクに下線を引くかどうかを指定する](how-to-specify-whether-a-hyperlink-is-underlined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb7ca-121">例</span><span class="sxs-lookup"><span data-stu-id="cb7ca-121">Example</span></span>  
 <span data-ttu-id="cb7ca-122">次のコード例の下線テキスト装飾では、既定のフォント値が使用されています。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="cb7ca-123">次のコード例の下線テキスト装飾は、ペンに対する単色ブラシで作成されています。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="cb7ca-124">次のコード例の下線テキスト装飾は、破線のペンに対する線状グラデーション ブラシで作成されています。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="cb7ca-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb7ca-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="cb7ca-126">ハイパーリンクに下線を引くかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="cb7ca-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
