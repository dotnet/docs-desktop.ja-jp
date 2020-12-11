---
title: '方法: 影付きテキストを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 2b5298a4cdc2cf12c3cf44d06589c584accc7800
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984707"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="ac879-102">方法: 影付きテキストを作成する</span><span class="sxs-lookup"><span data-stu-id="ac879-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="ac879-103">このセクションの例で、表示されるテキストに影を付ける方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ac879-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac879-104">例</span><span class="sxs-lookup"><span data-stu-id="ac879-104">Example</span></span>  
 <span data-ttu-id="ac879-105"><xref:System.Windows.Media.Effects.DropShadowEffect> オブジェクトを使用すると、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] オブジェクトにさまざまなドロップ シャドウ効果を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ac879-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="ac879-106">テキストにドロップ シャドウ効果を適用した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="ac879-107">この場合、影はソフト シャドウです。つまり、影の色がぼやけています。</span><span class="sxs-lookup"><span data-stu-id="ac879-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![ぼかし &#61; 0.25 のテキスト シャドウ](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="ac879-109"><xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> プロパティを設定することで、影の幅を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="ac879-110">値が `4.0` の場合、影の幅は 4 ピクセルになります。</span><span class="sxs-lookup"><span data-stu-id="ac879-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="ac879-111"><xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> プロパティを変更すると、影の柔らかさ、つまりぼかし具合を調整できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="ac879-112">値が `0.0` の場合、ぼかしはありません。</span><span class="sxs-lookup"><span data-stu-id="ac879-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="ac879-113">ソフト シャドウを付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="ac879-114">これらの影効果は、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] テキスト レンダリング パイプラインを通過しません。</span><span class="sxs-lookup"><span data-stu-id="ac879-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="ac879-115">結果として、これらの効果の利用時、ClearType が無効になります。</span><span class="sxs-lookup"><span data-stu-id="ac879-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="ac879-116">テキストにハード シャドウ効果を適用した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="ac879-117">この場合、影はぼかされません。</span><span class="sxs-lookup"><span data-stu-id="ac879-117">In this case, the shadow is not blurred.</span></span>  
  
 ![ぼかし &#61; 0 のテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 <span data-ttu-id="ac879-119"><xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> プロパティを `0.0` に設定してぼかしなしにすると、ハード シャドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="ac879-120"><xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> プロパティを変更すると、影の方向を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="ac879-121">このプロパティの方向値を `0` から `360` の角度に設定します。</span><span class="sxs-lookup"><span data-stu-id="ac879-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="ac879-122">次の図では、<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> プロパティ設定の方向値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![シャドウの DropShadow 度の設定](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="ac879-124">ハード シャドウを付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="ac879-125">ぼかし効果を使用する</span><span class="sxs-lookup"><span data-stu-id="ac879-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="ac879-126"><xref:System.Windows.Media.Effects.BlurBitmapEffect> を使用して、テキスト オブジェクトの後ろに配置できる影のような効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="ac879-127">テキストに適用されたぼかしビットマップ効果は、全方向に均等にテキストをぼかします。</span><span class="sxs-lookup"><span data-stu-id="ac879-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="ac879-128">テキストにぼかし効果が適用されている例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![BlurBitmapEffect を使用するテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="ac879-130">ぼかし効果を付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="ac879-131">TranslateTransform を使用する</span><span class="sxs-lookup"><span data-stu-id="ac879-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="ac879-132"><xref:System.Windows.Media.TranslateTransform> を使用して、テキスト オブジェクトの後ろに配置できる影のような効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac879-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="ac879-133">次のコード例では、<xref:System.Windows.Media.TranslateTransform> を使用してテキストに影のような効果を付けています。</span><span class="sxs-lookup"><span data-stu-id="ac879-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="ac879-134">この例では、メインのテキストの下にわずかに中心をずらしたコピーが付き、影のような効果を作っています。</span><span class="sxs-lookup"><span data-stu-id="ac879-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![TranslateTransform を使用するテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 <span data-ttu-id="ac879-136">TranslateTransform を利用して影のような効果を付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="ac879-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
