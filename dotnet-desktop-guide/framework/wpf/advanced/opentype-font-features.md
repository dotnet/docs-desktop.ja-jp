---
title: OpenType フォントの機能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: 5f9f5b14400962af2da94dd60f5170cb2f3d2f51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980251"
---
# <a name="opentype-font-features"></a><span data-ttu-id="14f99-102">OpenType フォントの機能</span><span class="sxs-lookup"><span data-stu-id="14f99-102">OpenType Font Features</span></span>

<span data-ttu-id="14f99-103">このトピックでは、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] における OpenType フォント技術の主要機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="14f99-103">This topic provides an overview of some of the key features of OpenType font technology in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
<a name="overview"></a>

## <a name="opentype-font-format"></a><span data-ttu-id="14f99-104">OpenType フォントの書式</span><span class="sxs-lookup"><span data-stu-id="14f99-104">OpenType Font Format</span></span>  

 <span data-ttu-id="14f99-105">OpenType フォント形式は TrueType® フォント形式が拡張されたものであり、PostScript フォント データのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-105">The OpenType font format is an extension of the TrueType® font format, adding support for PostScript font data.</span></span> <span data-ttu-id="14f99-106">OpenType フォント形式は、Microsoft と Adobe Corporation により共同開発されました。</span><span class="sxs-lookup"><span data-stu-id="14f99-106">The OpenType font format was developed jointly by Microsoft and Adobe Corporation.</span></span> <span data-ttu-id="14f99-107">OpenType フォントおよび OpenType フォントをサポートするオペレーティング システム サービスでは、フォントに TrueType アウトラインまたは CFF (PostScript) アウトラインのどちらが含まれていても、ユーザーは簡単な方法でフォントをインストールして使用できます。</span><span class="sxs-lookup"><span data-stu-id="14f99-107">OpenType fonts and the operating system services which support OpenType fonts provide users with a simple way to install and use fonts, whether the fonts contain TrueType outlines or CFF (PostScript) outlines.</span></span>  
  
 <span data-ttu-id="14f99-108">OpenType フォント形式では、次のような開発者の課題が対処されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-108">The OpenType font format addresses the following developer challenges:</span></span>  
  
- <span data-ttu-id="14f99-109">より広範なマルチプラットフォームのサポート。</span><span class="sxs-lookup"><span data-stu-id="14f99-109">Broader multi-platform support.</span></span>  
  
- <span data-ttu-id="14f99-110">国際文字セットのサポート強化。</span><span class="sxs-lookup"><span data-stu-id="14f99-110">Better support for international character sets.</span></span>  
  
- <span data-ttu-id="14f99-111">フォント データの保護強化。</span><span class="sxs-lookup"><span data-stu-id="14f99-111">Better protection for font data.</span></span>  
  
- <span data-ttu-id="14f99-112">ファイルのサイズを小さくして、より効率的にフォントを配布。</span><span class="sxs-lookup"><span data-stu-id="14f99-112">Smaller file sizes to make font distribution more efficient.</span></span>  
  
- <span data-ttu-id="14f99-113">高度なテキスト編集コントロールの幅広いサポート。</span><span class="sxs-lookup"><span data-stu-id="14f99-113">Broader support for advanced typographic control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14f99-114">Windows SDK には、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] アプリケーションで使用できるサンプルの OpenType フォント セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14f99-114">The Windows SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="14f99-115">これらのフォントでは、このトピックで説明していく機能の大半が提供されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-115">These fonts provide most of the features illustrated in the rest of this topic.</span></span> <span data-ttu-id="14f99-116">詳細については、「[OpenType フォント パックのサンプル](sample-opentype-font-pack.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f99-116">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<span data-ttu-id="14f99-117">OpenType フォント形式の詳細については、「[OpenType の仕様](/typography/opentype/spec/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f99-117">For details of the OpenType font format, see the [OpenType specification](/typography/opentype/spec/).</span></span>  
  
### <a name="advanced-typographic-extensions"></a><span data-ttu-id="14f99-118">高度なテキスト編集の拡張機能</span><span class="sxs-lookup"><span data-stu-id="14f99-118">Advanced Typographic Extensions</span></span>  

 <span data-ttu-id="14f99-119">高度な印刷用テーブル (OpenType レイアウト テーブル) では、TrueType または CFF のアウトラインを使用してフォントの機能が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-119">The Advanced Typographic tables (OpenType Layout tables) extend the functionality of fonts with either TrueType or CFF outlines.</span></span> <span data-ttu-id="14f99-120">OpenType レイアウトのフォントには、フォントの機能を拡張する追加の情報が含まれ、高品質の国際タイポグラフィがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-120">OpenType Layout fonts contain additional information that extends the capabilities of the fonts to support high-quality international typography.</span></span> <span data-ttu-id="14f99-121">ほとんどの OpenType フォントでは、利用可能な OpenType 機能全体のサブセットのみが公開されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-121">Most OpenType fonts expose only a subset of the total OpenType features available.</span></span> <span data-ttu-id="14f99-122">OpenType フォントでは次のような機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-122">OpenType fonts provide the following features.</span></span>  
  
- <span data-ttu-id="14f99-123">合字、位置フォーム、代替、およびその他のフォント置換をサポートする、文字とグリフの間の充実したマッピング。</span><span class="sxs-lookup"><span data-stu-id="14f99-123">Rich mapping between characters and glyphs that support ligatures, positional forms, alternates, and other font substitutions.</span></span>  
  
- <span data-ttu-id="14f99-124">2 次元配置とグリフ結合のサポート。</span><span class="sxs-lookup"><span data-stu-id="14f99-124">Support for two-dimensional positioning and glyph attachment.</span></span>  
  
- <span data-ttu-id="14f99-125">フォントには明示的なスクリプトと言語情報が含まれるため、テキスト処理アプリケーションはそれに従って動作を調整可能。</span><span class="sxs-lookup"><span data-stu-id="14f99-125">Explicit script and language information contained in font, so a text-processing application can adjust its behavior accordingly.</span></span>  
  
 <span data-ttu-id="14f99-126">OpenType レイアウト テーブルについては、OpenType 仕様の ["フォント ファイル テーブル"](https://www.microsoft.com/typography/otspec/otff.htm) に関するセクションで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-126">The OpenType Layout tables are described in more detail in the ["Font File Tables"](https://www.microsoft.com/typography/otspec/otff.htm) section of the OpenType specification.</span></span>  
  
 <span data-ttu-id="14f99-127">この概要のこれ以降では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティによって公開される、視覚的に興味深い OpenType の機能の幅広さと柔軟性について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f99-127">The remainder of this overview introduces the breadth and flexibility of some of the visually-interesting OpenType features that are exposed by the properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="14f99-128">このオブジェクトの詳細については、「[タイポグラフィ クラス](#typography_class)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f99-128">For more information on this object, see [Typography Class](#typography_class).</span></span>  
  
<a name="variants"></a>

## <a name="variants"></a><span data-ttu-id="14f99-129">バリアント</span><span class="sxs-lookup"><span data-stu-id="14f99-129">Variants</span></span>  

 <span data-ttu-id="14f99-130">バリアントを使用して、上付き文字と下付きなどのさまざまなタイポグラフィ スタイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-130">Variants are used to render different typographic styles, such as superscripts and subscripts.</span></span>  
  
### <a name="superscripts-and-subscripts"></a><span data-ttu-id="14f99-131">上付き/下付きの文字</span><span class="sxs-lookup"><span data-stu-id="14f99-131">Superscripts and Subscripts</span></span>  

 <span data-ttu-id="14f99-132"><xref:System.Windows.Documents.Typography.Variants%2A> プロパティを使用すると、OpenType フォントに上付き文字と下付き文字の値を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="14f99-132">The <xref:System.Windows.Documents.Typography.Variants%2A> property allows you to set superscript and subscript values for an OpenType font.</span></span>  
  
 <span data-ttu-id="14f99-133">次のテキストは、Palatino Linotype フォントの上付き文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-133">The following text displays superscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="14f99-134">![OpenType の上付き文字を使用するテキスト](./media/opentype-font-features/opentype-superscripts.gif "OpenType の上付き文字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-134">![Text using OpenType superscripts](./media/opentype-font-features/opentype-superscripts.gif "Text using OpenType superscripts")</span></span>  
  
 <span data-ttu-id="14f99-135">次に示すマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Palatino Linotype フォントの上付き文字を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="14f99-135">The following markup example shows how to define superscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 <span data-ttu-id="14f99-136">次のテキストは、Palatino Linotype フォントの下付き文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-136">The following text displays subscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="14f99-137">![OpenType の下付き文字を使用するテキスト](./media/opentype-font-features/opentype-subscripts.gif "OpenType の下付き文字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-137">![Text using OpenType subscripts](./media/opentype-font-features/opentype-subscripts.gif "Text using OpenType subscripts")</span></span>  
  
 <span data-ttu-id="14f99-138">次に示すマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Palatino Linotype フォントの下付き文字を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="14f99-138">The following markup example shows how to define subscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a><span data-ttu-id="14f99-139">上付き文字と下付き文字の装飾的な用途</span><span class="sxs-lookup"><span data-stu-id="14f99-139">Decorative Uses of Superscripts and Subscripts</span></span>  

 <span data-ttu-id="14f99-140">上付き文字と下付き文字を使用して、大文字と小文字が混在したテキストに装飾的効果をつけることもできます。</span><span class="sxs-lookup"><span data-stu-id="14f99-140">You can also use superscripts and subscripts to create decorative effects of mixed case text.</span></span> <span data-ttu-id="14f99-141">次のテキストは、Palatino Linotype フォントの上付き文字と下付き文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-141">The following text displays superscript and subscript text for the Palatino Linotype font.</span></span> <span data-ttu-id="14f99-142">大文字には影響がないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="14f99-142">Note that the capitals are not affected.</span></span>  
  
 <span data-ttu-id="14f99-143">![OpenType の上付き文字と下付き文字を使用するテキスト](./media/opentype-font-features/opentype-superscripts-subscripts.gif "OpenType の上付き文字と下付き文字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-143">![Text using OpenType superscripts and subscripts](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Text using OpenType superscripts and subscripts")</span></span>  

 <span data-ttu-id="14f99-144">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用してフォントの上付き文字と下付き文字を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-144">The following markup example shows how to define superscripts and subscripts for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>

## <a name="capitals"></a><span data-ttu-id="14f99-145">大文字</span><span class="sxs-lookup"><span data-stu-id="14f99-145">Capitals</span></span>  

 <span data-ttu-id="14f99-146">大文字は、大文字スタイルのグリフでテキストをレンダリングするタイポグラフィ形式のセットです。</span><span class="sxs-lookup"><span data-stu-id="14f99-146">Capitals are a set of typographical forms that render text in capital-styled glyphs.</span></span> <span data-ttu-id="14f99-147">通常、テキストをすべて大文字で表示すると、文字間隔が狭すぎるように見え、文字の印象と縦横比が重すぎるように感じられます。</span><span class="sxs-lookup"><span data-stu-id="14f99-147">Typically, when text is rendered as all capitals, the spacing between letters can appear too tight, and the weight and proportion of the letters too heavy.</span></span> <span data-ttu-id="14f99-148">OpenType では、小型英大文字、超小型英大文字、タイトル用、大文字スペーシングを含め、大文字に関する多くのスタイル形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-148">OpenType supports a number of styling formats for capitals, including small capitals, petite capitals, titling, and capital spacing.</span></span> <span data-ttu-id="14f99-149">これらのスタイル形式を使用して、英大文字の外観を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="14f99-149">These styling formats allow you to control the appearance of capitals.</span></span>  
  
 <span data-ttu-id="14f99-150">次のテキストは、Pescadero フォントの標準の大文字と、その後に "SmallCaps" および "AllSmallCaps" のスタイルをあてた文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-150">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="14f99-151">この例では、3 つの単語すべてに同じフォント サイズが使用されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-151">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="14f99-152">![OpenType の大文字を使用するテキスト](./media/opentype-font-features/opentype-capitals.gif "OpenType の大文字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-152">![Text using OpenType capitals](./media/opentype-font-features/opentype-capitals.gif "Text using OpenType capitals")</span></span>  
  
 <span data-ttu-id="14f99-153">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pescadero フォントの大文字を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-153">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="14f99-154">"SmallCaps" 形式を使用する場合は、先頭の大文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-154">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a><span data-ttu-id="14f99-155">タイトル用大文字</span><span class="sxs-lookup"><span data-stu-id="14f99-155">Titling Capitals</span></span>  

 <span data-ttu-id="14f99-156">タイトル用大文字は、重みと縦横比が軽く、標準の大文字よりも洗練された印象を与えるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-156">Titling capitals are lighter in weight and proportion and designed to give a more elegant look than normal capitals.</span></span> <span data-ttu-id="14f99-157">タイトル用大文字は通常、見出しとして大きいフォント サイズで使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-157">Titling capitals are typically used in larger font sizes as headings.</span></span> <span data-ttu-id="14f99-158">次のテキストは、Pescadero フォントの標準の大文字とタイトル用大文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-158">The following text displays normal and titling capitals for the Pescadero font.</span></span> <span data-ttu-id="14f99-159">2 行目のテキストの縦線の幅が狭いことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14f99-159">Notice the narrower stem widths of the text on the second line.</span></span>  
  
 <span data-ttu-id="14f99-160">![OpenType のタイトル大文字を使用するテキスト](./media/opentype-font-features/opentype-titling-capitals.gif "OpenType のタイトル大文字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-160">![Text using OpenType titling capitals](./media/opentype-font-features/opentype-titling-capitals.gif "Text using OpenType titling capitals")</span></span>  
  
 <span data-ttu-id="14f99-161">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pescadero フォントのタイトル用大文字を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-161">The following markup example shows how to define titling capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a><span data-ttu-id="14f99-162">大文字スペーシング</span><span class="sxs-lookup"><span data-stu-id="14f99-162">Capital Spacing</span></span>  

 <span data-ttu-id="14f99-163">大文字スペーシングは、テキストをすべて大文字にする場合に間隔を広くする機能です。</span><span class="sxs-lookup"><span data-stu-id="14f99-163">Capital spacing is a feature that allows you to provide more spacing when using all capitals in text.</span></span> <span data-ttu-id="14f99-164">大文字は、通常、小文字と調和するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-164">Capital letters are typically designed to blend with lowercase letters.</span></span> <span data-ttu-id="14f99-165">大文字と小文字の間では適切に見えるスペーシングでも、大文字だけが使用されている場合は、狭すぎるように見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="14f99-165">Spacing that appears attractive between and a capital letter and a lowercase letter may look too tight when all capital letters are used.</span></span> <span data-ttu-id="14f99-166">次のテキストは、Pescadero フォントの標準のスペーシングと大文字スペーシングを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-166">The following text displays normal and capital spacing for the Pescadero font.</span></span>  
  
 <span data-ttu-id="14f99-167">![OpenType の大文字スペーシングを使用するテキスト](./media/opentype-font-features/opentype-capital-spacing.gif "OpenType の大文字スペーシングを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-167">![Text using OpenType capital spacing](./media/opentype-font-features/opentype-capital-spacing.gif "Text using OpenType capital spacing")</span></span>  

 <span data-ttu-id="14f99-168">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pescadero フォントの大文字スペーシングを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-168">The following markup example shows how to define capital spacing for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>

## <a name="ligatures"></a><span data-ttu-id="14f99-169">合字</span><span class="sxs-lookup"><span data-stu-id="14f99-169">Ligatures</span></span>  

 <span data-ttu-id="14f99-170">合字とは、2 つ以上のグリフを、より読みやすい、あるいはより魅力的なテキストにするために、1 つのグリフに形成したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-170">Ligatures are two or more glyphs that are formed into a single glyph in order to create more readable or attractive text.</span></span> <span data-ttu-id="14f99-171">OpenType フォントでは、4 種類の合字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-171">OpenType fonts support four types of ligatures:</span></span>  
  
- <span data-ttu-id="14f99-172">**標準合字**。</span><span class="sxs-lookup"><span data-stu-id="14f99-172">**Standard ligatures**.</span></span> <span data-ttu-id="14f99-173">読みやすさを高めるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-173">Designed to enhance readability.</span></span> <span data-ttu-id="14f99-174">標準合字には、"fi"、"fl" および "ff" があります。</span><span class="sxs-lookup"><span data-stu-id="14f99-174">Standard ligatures include "fi", "fl", and "ff".</span></span>  
  
- <span data-ttu-id="14f99-175">**コンテキスト合字**。</span><span class="sxs-lookup"><span data-stu-id="14f99-175">**Contextual ligatures**.</span></span> <span data-ttu-id="14f99-176">合字を構成する文字の間の結合を向上させることによって、読みやすさを高めるよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-176">Designed to enhance readability by providing better joining behavior between the characters that make up the ligature.</span></span>  
  
- <span data-ttu-id="14f99-177">**随意合字**。</span><span class="sxs-lookup"><span data-stu-id="14f99-177">**Discretionary ligatures**.</span></span> <span data-ttu-id="14f99-178">装飾を加える設計で、特に読みやすくなるようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="14f99-178">Designed to be ornamental, and not specifically designed for readability.</span></span>  
  
- <span data-ttu-id="14f99-179">**歴史的合字**。</span><span class="sxs-lookup"><span data-stu-id="14f99-179">**Historical ligatures**.</span></span> <span data-ttu-id="14f99-180">歴史的な記述に相応しい設計で、特に読みやすくなるようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="14f99-180">Designed to be historical, and not specifically designed for readability.</span></span>  
  
 <span data-ttu-id="14f99-181">次のテキストは、Pericles フォントの標準合字グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-181">The following text displays standard ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="14f99-182">![OpenType の標準合字を使用するテキスト](./media/opentype-font-features/opentype-standard-ligatures.gif "OpenType の標準合字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-182">![Text using OpenType standard ligatures](./media/opentype-font-features/opentype-standard-ligatures.gif "Text using OpenType standard ligatures")</span></span>  
  
 <span data-ttu-id="14f99-183">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pericles フォントの標準合字グリフを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-183">The following markup example shows how to define standard ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 <span data-ttu-id="14f99-184">次のテキストは、Pericles フォントの随意合字グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-184">The following text displays discretionary ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="14f99-185">![OpenType の随意合字を使用するテキスト](./media/opentype-font-features/opentype-discretionary-ligatures.gif "OpenType の随意合字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-185">![Text using OpenType discretionary ligatures](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Text using OpenType discretionary ligatures")</span></span>  
  
 <span data-ttu-id="14f99-186">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pericles フォントの随意合字グリフを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-186">The following markup example shows how to define discretionary ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 <span data-ttu-id="14f99-187">既定では、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の OpenType フォントでは標準合字が有効です。</span><span class="sxs-lookup"><span data-stu-id="14f99-187">By default, OpenType fonts in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] enable standard ligatures.</span></span> <span data-ttu-id="14f99-188">たとえば、Palatino Linotype フォントを使用する場合、標準合字 "fi"、"ff" および "fl" は組み合わせ文字グリフとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-188">For example, if you use the Palatino Linotype font, the standard ligatures "fi", "ff", and "fl" appear as a combined character glyph.</span></span> <span data-ttu-id="14f99-189">各標準合字では文字のペアが相互に接していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14f99-189">Notice that the pair of characters for each standard ligature touch each other.</span></span>  
  
 <span data-ttu-id="14f99-190">![Palatino Linotype で OpenType の標準合字を使用するテキスト](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Palatino Linotype で OpenType の標準合字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-190">![Text using OpenType standard ligatures with Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Text using OpenType standard ligatures with Palatino Linotype")</span></span>

 <span data-ttu-id="14f99-191">ただし、標準合字機能を無効にして、"ff" などの標準合字が、組み合わせ文字グリフとしてではなく、2 つの別々のグリフとして表示されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="14f99-191">However, you can disable standard ligature features so that a standard ligature such as "ff" displays as two separate glyphs, rather than as a combined character glyph.</span></span>  
  
 <span data-ttu-id="14f99-192">![OpenType の無効な標準合字を使用するテキスト](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "OpenType の無効な標準合字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-192">![Text using disabled OpenType standard ligatures](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Text using disabled OpenType standard ligatures")</span></span>  

 <span data-ttu-id="14f99-193">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Palatino Linotype フォントの標準合字グリフを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-193">The following markup example shows how to disable standard ligature glyphs for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>

## <a name="swashes"></a><span data-ttu-id="14f99-194">飾り付き</span><span class="sxs-lookup"><span data-stu-id="14f99-194">Swashes</span></span>  

 <span data-ttu-id="14f99-195">飾り付きは装飾的なグリフで、カリグラフィを連想させる、手の込んだ装飾が使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-195">Swashes are decorative glyphs that use elaborate ornamentation often associated with calligraphy.</span></span> <span data-ttu-id="14f99-196">次のテキストは、Pescadero フォントの標準および飾り付きグリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-196">The following text displays standard and swash glyphs for the Pescadero font.</span></span>  
  
 <span data-ttu-id="14f99-197">![OpenType の標準グリフとスワッシュ グリフを使用するテキスト](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "OpenType の標準グリフと飾り付きグリフを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-197">![Text using OpenType standard and swash glyphs](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Text using OpenType standard and swash glyphs")</span></span>  

 <span data-ttu-id="14f99-198">飾り付きは、季節のご挨拶などの短いフレーズで装飾的な要素としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-198">Swashes are often used as decorative elements in short phrases such as event announcements.</span></span> <span data-ttu-id="14f99-199">次のテキストでは、飾り付きを使用して、イベントの名前の大文字を強調しています。</span><span class="sxs-lookup"><span data-stu-id="14f99-199">The following text uses swashes to emphasize the capital letters of the name of the event.</span></span>  
  
 <span data-ttu-id="14f99-200">![OpenType の飾り付きを使用するテキスト](./media/opentype-font-features/opentype-swashes.gif "OpenType の巻き髭を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-200">![Text using OpenType swashes](./media/opentype-font-features/opentype-swashes.gif "Text using OpenType swashes")</span></span>  
  
 <span data-ttu-id="14f99-201">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用してフォントの飾り付きを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-201">The following markup example shows how to define swashes for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a><span data-ttu-id="14f99-202">コンテキスト飾り付き</span><span class="sxs-lookup"><span data-stu-id="14f99-202">Contextual Swashes</span></span>  

 <span data-ttu-id="14f99-203">飾り付きグリフの特定の組み合わせでは、隣りあう文字の下に延びる部分が重なり合うなど、美しくない外観になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14f99-203">Certain combinations of swash glyphs can cause an unattractive appearance, such as overlapping descenders on adjacent letters.</span></span> <span data-ttu-id="14f99-204">コンテキスト飾り付きを使用すると、より良い外観を生成する代替の飾り付きグリフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="14f99-204">Using a contextual swash allows you to use a substitute swash glyph that produces a better appearance.</span></span> <span data-ttu-id="14f99-205">次のテキストでは、コンテキスト飾り付きが適用される前後の同じ単語を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-205">The following text shows the same word before and after a contextual swash is applied.</span></span>  
  
 <span data-ttu-id="14f99-206">![OpenType のコンテキスト飾り付きを使用するテキスト](./media/opentype-font-features/opentype-contextual-swashes.gif "OpenType のコンテキスト巻き髭を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-206">![Text using OpenType contextual swashes](./media/opentype-font-features/opentype-contextual-swashes.gif "Text using OpenType contextual swashes")</span></span>  
  
 <span data-ttu-id="14f99-207">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pescadero フォントのコンテキスト飾り付きを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-207">The following markup example shows how to define a contextual swash for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>

## <a name="alternates"></a><span data-ttu-id="14f99-208">代替</span><span class="sxs-lookup"><span data-stu-id="14f99-208">Alternates</span></span>  

 <span data-ttu-id="14f99-209">代替文字は、標準的なグリフの代わりに使用できるグリフです。</span><span class="sxs-lookup"><span data-stu-id="14f99-209">Alternates are glyphs that can be substituted for a standard glyph.</span></span> <span data-ttu-id="14f99-210">次の例で使用される Pericles フォントなどの OpenType フォントには、テキストの異なる外観を作るのに使用できる代替グリフを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="14f99-210">OpenType fonts, such as the Pericles font used in the following examples, can contain alternate glyphs that you can use to create different appearances for text.</span></span> <span data-ttu-id="14f99-211">次のテキストは、Pericles フォントの標準グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-211">The following text displays standard glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="14f99-212">![OpenType の標準グリフを使用するテキスト](./media/opentype-font-features/opentype-standard-glyphs.gif "OpenType の標準グリフを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-212">![Text using OpenType standard glyphs](./media/opentype-font-features/opentype-standard-glyphs.gif "Text using OpenType standard glyphs")</span></span>  

 <span data-ttu-id="14f99-213">Pericles OpenType フォントには、標準グリフ セットにスタイル代替グリフを提供する追加グリフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14f99-213">The Pericles OpenType font contains additional glyphs that provide stylistic alternates to the standard set of glyphs.</span></span> <span data-ttu-id="14f99-214">次のテキストでは、スタイル代替グリフが表示されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-214">The following text displays stylistic alternate glyphs.</span></span>  
  
 <span data-ttu-id="14f99-215">![OpenType のスタイル代替グリフを使用するテキスト](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "OpenType のスタイル代替グリフを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-215">![Text using OpenType stylistic alternate glyphs](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Text using OpenType stylistic alternate glyphs")</span></span>  
  
 <span data-ttu-id="14f99-216">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pericles フォントのスタイル代替グリフを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-216">The following markup example shows how to define stylistic alternate glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 <span data-ttu-id="14f99-217">次のテキストは、Pericles フォントの他のスタイル代替グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-217">The following text displays several other stylistic alternate glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="14f99-218">![Pericles フォントの OpenType スタイル代替グリフを使用するテキスト](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Pericles フォントの OpenType スタイル代替グリフを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-218">![Text using OpenType stylistic alternate glyphs  for the Pericles font](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Text using OpenType stylistic alternate glyphs  for the Pericles font")</span></span>

 <span data-ttu-id="14f99-219">次のマークアップの例では、これらの他のスタイル代替グリフを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-219">The following markup example shows how to define these other stylistic alternate glyphs.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a><span data-ttu-id="14f99-220">ランダムなコンテキスト代替</span><span class="sxs-lookup"><span data-stu-id="14f99-220">Random Contextual Alternates</span></span>  

 <span data-ttu-id="14f99-221">ランダムなコンテキスト代替は、単一文字に複数の代替グリフを提供します。</span><span class="sxs-lookup"><span data-stu-id="14f99-221">Random contextual alternates provide multiple substitute glyphs for a single character.</span></span> <span data-ttu-id="14f99-222">スクリプト型フォントで実装されたこの機能では、ランダムに選択された外観がわずかに異なるグリフのセットを使用して、手書きをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="14f99-222">When implemented with script-type fonts, this feature can simulate handwriting by using of a set of randomly chosen glyphs with slight differences in appearance.</span></span> <span data-ttu-id="14f99-223">次のテキストでは、Lindsey フォントに対してランダムなコンテキスト代替が使用されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-223">The following text uses random contextual alternates for the Lindsey font.</span></span> <span data-ttu-id="14f99-224">文字 "a" の外観が少し異なることに注意してください</span><span class="sxs-lookup"><span data-stu-id="14f99-224">Notice that the letter "a" varies slightly in appearance</span></span>  
  
 <span data-ttu-id="14f99-225">![OpenType のランダムなコンテキスト代替を使用するテキスト](./media/opentype-font-features/opentype-random-contextual-alternates.gif "OpenType のランダムなコンテキスト代替を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-225">![Text using OpenType random contextual alternates](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Text using OpenType random contextual alternates")</span></span>  
  
 <span data-ttu-id="14f99-226">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Lindsey フォントのランダムなコンテキスト代替を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-226">The following markup example shows how to define random contextual alternates for the Lindsey font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a><span data-ttu-id="14f99-227">歴史的形式</span><span class="sxs-lookup"><span data-stu-id="14f99-227">Historical Forms</span></span>  

 <span data-ttu-id="14f99-228">歴史的形式は、過去に一般的であった表示形式です。</span><span class="sxs-lookup"><span data-stu-id="14f99-228">Historical forms are typographic conventions that were common in the past.</span></span> <span data-ttu-id="14f99-229">次のテキストでは、Palatino Linotype フォントのグリフの歴史的形式を使用して、"Boston, Massachusetts" という語句が表示されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-229">The following text displays the phrase, "Boston, Massachusetts", using an historical form of glyphs for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="14f99-230">![OpenType の歴史的形式を使用するテキスト](./media/opentype-font-features/opentype-historical-forms.gif "OpenType の履歴フォームを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-230">![Text using OpenType historical forms](./media/opentype-font-features/opentype-historical-forms.gif "Text using OpenType historical forms")</span></span>  

 <span data-ttu-id="14f99-231">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Palatino Linotype フォントの歴史的形式を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-231">The following markup example shows how to define historical forms for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>

## <a name="numerical-styles"></a><span data-ttu-id="14f99-232">数値スタイル</span><span class="sxs-lookup"><span data-stu-id="14f99-232">Numerical Styles</span></span>  

 <span data-ttu-id="14f99-233">OpenType フォントでは、テキスト内の数値に使用できる数多くの機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="14f99-233">OpenType fonts support a large number of features that can be used with numerical values in text.</span></span>  
  
### <a name="fractions"></a><span data-ttu-id="14f99-234">小数</span><span class="sxs-lookup"><span data-stu-id="14f99-234">Fractions</span></span>  

 <span data-ttu-id="14f99-235">OpenType フォントでは、スラッシュや横棒を使用した小数スタイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-235">OpenType fonts support styles for fractions, including slashed and stacked.</span></span>  
  
 <span data-ttu-id="14f99-236">次のテキストは、Palatino Linotype フォントの小数スタイルを示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-236">The following text displays fraction styles for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="14f99-237">![OpenType の分数 (横) と分数 (縦) を使用するテキスト](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "OpenType の分数 (横) と分数 (縦) を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-237">![Text using OpenType slashed and stacked fractions](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Text using OpenType slashed and stacked fractions")</span></span>  

 <span data-ttu-id="14f99-238">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Palatino Linotype フォントの小数スタイルを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-238">The following markup example shows how to define fraction styles for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a><span data-ttu-id="14f99-239">旧式スタイルの数字</span><span class="sxs-lookup"><span data-stu-id="14f99-239">Old Style Numerals</span></span>  

 <span data-ttu-id="14f99-240">OpenType フォントでは、旧式スタイルの数字形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-240">OpenType fonts support an old style numeral format.</span></span> <span data-ttu-id="14f99-241">この形式は、もはや標準ではなくなったスタイルで数字を表示するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="14f99-241">This format is useful for displaying numerals in styles that are no longer standard.</span></span> <span data-ttu-id="14f99-242">次のテキストは、Palatino Linotype フォントの標準と旧式のスタイルの数字形式で、18 世紀の日付を表示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-242">The following text displays an 18th century date in standard and old style numeral formats for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="14f99-243">![OpenType の旧式スタイルの数字を使用するテキスト](./media/opentype-font-features/opentype-old-style-numerals.gif "OpenType の古いスタイルの数字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-243">![Text using OpenType old style numerals](./media/opentype-font-features/opentype-old-style-numerals.gif "Text using OpenType old style numerals")</span></span>  

 <span data-ttu-id="14f99-244">次のテキストは、Palatino Linotype フォントの標準の数字と、旧式スタイルの数字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-244">The following text displays standard numerals for the Palatino Linotype font, followed by old style numerals.</span></span>  
  
 <span data-ttu-id="14f99-245">![OpenType の旧式スタイルの数字セットを使用するテキスト](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "OpenType の古いスタイルの数字セットを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-245">![Text using OpenType old style numeral sets](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Text using OpenType old style numeral sets")</span></span>  
  
 <span data-ttu-id="14f99-246">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Palatino Linotype フォントの旧式スタイルの数値を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-246">The following markup example shows how to define old style numerals for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a><span data-ttu-id="14f99-247">プロポーショナルと表形式の数字</span><span class="sxs-lookup"><span data-stu-id="14f99-247">Proportional and Tabular Figures</span></span>  

 <span data-ttu-id="14f99-248">OpenType フォントでは、プロポーショナルと表形式の数字の機能がサポートされており、数字を使用するときの幅の調整が制御されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-248">OpenType fonts support a proportional and tabular figure feature to control the alignment of widths when using numerals.</span></span> <span data-ttu-id="14f99-249">プロポーショナルの数字では、それぞれの数字は異なる幅を持つものとして扱われます。たとえば "1" は "5" より狭い幅です。</span><span class="sxs-lookup"><span data-stu-id="14f99-249">Proportional figures treat each numeral as having a different width—"1" is narrower than "5".</span></span> <span data-ttu-id="14f99-250">表形式の数字は、横が揃うように等幅の数字として処理されるため、財務に関する情報が読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="14f99-250">Tabular figures are treated as equal-width numerals so that they align vertically, which increases the readability of financial type information.</span></span>  
  
 <span data-ttu-id="14f99-251">1 列目のテキストは、Miramonte フォントを使用して表示された 2 つのプロポーショナルの数字です。</span><span class="sxs-lookup"><span data-stu-id="14f99-251">The following text displays two proportional figures in the first column using the Miramonte font.</span></span> <span data-ttu-id="14f99-252">数字 "5" と "1" の幅の違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14f99-252">Note the difference in width between the numerals "5" and "1".</span></span> <span data-ttu-id="14f99-253">2 列目には、同じ 2 つの数値が表形式の数字機能を使用して横幅を調整されて表示されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-253">The second column shows the same two numeric values with the widths adjusted by using the tabular figure feature.</span></span>  
  
 <span data-ttu-id="14f99-254">![OpenType のプロポーショナルと表形式の数字を使用するテキスト](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "OpenType のプロポーショナルと表形式の数字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-254">![Text using OpenType proportional & tabular figures](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Text using OpenType proportional and tabular figures")</span></span>  

 <span data-ttu-id="14f99-255">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Miramonte フォントのプロポーショナルと表形式の数字を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-255">The following markup example shows how to define proportional and tabular figures for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a><span data-ttu-id="14f99-256">スラッシュ付きゼロ</span><span class="sxs-lookup"><span data-stu-id="14f99-256">Slashed Zero</span></span>  

 <span data-ttu-id="14f99-257">OpenType フォントでは、英文字 "O" と数字の "0" の違いを強調するためのスラッシュ付きゼロの数字形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14f99-257">OpenType fonts support a slashed zero numeral format to emphasize the difference between the letter "O" and the numeral "0".</span></span> <span data-ttu-id="14f99-258">スラッシュ付きゼロは、財務およびビジネス情報における ID によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-258">The slashed zero numeral is often used for identifiers in financial and business information.</span></span>  
  
 <span data-ttu-id="14f99-259">次のテキストは、Miramonte フォントを使用してサンプルの注文識別子を表示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-259">The following text displays a sample order identifier using the Miramonte font.</span></span> <span data-ttu-id="14f99-260">1 行目では、標準の数字が使用されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-260">The first line uses standard numerals.</span></span> <span data-ttu-id="14f99-261">2 行目では、大文字の "O" と区別しやすいように、スラッシュ付きゼロの数字が使用されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-261">The second line used slashed zero numerals to provide better contrast with the uppercase "O" letter.</span></span>  
  
 <span data-ttu-id="14f99-262">![OpenType のスラッシュ付きのゼロを使用するテキスト](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "OpenType のスラッシュ付きのゼロを使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-262">![Text using OpenType slashed zero numerals](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Text using OpenType slashed zero numerals")</span></span>  

 <span data-ttu-id="14f99-263">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Miramonte フォントのスラッシュ付きのゼロ数値を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-263">The following markup example shows how to define slashed zero numerals for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>

## <a name="typography-class"></a><span data-ttu-id="14f99-264">タイポグラフィ クラス</span><span class="sxs-lookup"><span data-stu-id="14f99-264">Typography Class</span></span>  

 <span data-ttu-id="14f99-265"><xref:System.Windows.Documents.Typography> オブジェクトでは、OpenType フォントでサポートされる機能セットが公開されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-265">The <xref:System.Windows.Documents.Typography> object exposes the set of features that an OpenType font supports.</span></span> <span data-ttu-id="14f99-266">マークアップで <xref:System.Windows.Documents.Typography> プロパティを設定することにより、OpenType 機能を利用したドキュメントを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="14f99-266">By setting the properties of <xref:System.Windows.Documents.Typography> in markup, you can easily author documents that take advantage of OpenType features.</span></span>  
  
 <span data-ttu-id="14f99-267">次のテキストは、Pescadero フォントの標準の大文字と、その後に "SmallCaps" および "AllSmallCaps" のスタイルをあてた文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="14f99-267">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="14f99-268">この例では、3 つの単語すべてに同じフォント サイズが使用されています。</span><span class="sxs-lookup"><span data-stu-id="14f99-268">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="14f99-269">![OpenType の大文字を使用するテキスト](./media/opentype-font-features/opentype-capitals.gif "OpenType の大文字を使用するテキスト")</span><span class="sxs-lookup"><span data-stu-id="14f99-269">![Text using OpenType capitals](./media/opentype-font-features/opentype-capitals.gif "Text using OpenType capitals")</span></span>  

 <span data-ttu-id="14f99-270">次のマークアップの例では、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティを使用して Pescadero フォントの大文字を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14f99-270">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="14f99-271">"SmallCaps" 形式を使用する場合は、先頭の大文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="14f99-271">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 <span data-ttu-id="14f99-272">次のコード例では、前のマークアップの例と同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f99-272">The following code example accomplishes the same task as the previous markup example.</span></span>  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a><span data-ttu-id="14f99-273">タイポグラフィ クラスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="14f99-273">Typography Class Properties</span></span>  

 <span data-ttu-id="14f99-274">次の表は、<xref:System.Windows.Documents.Typography> オブジェクトのプロパティ、値、既定値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="14f99-274">The following table lists the properties, values, and default settings of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
|<span data-ttu-id="14f99-275">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14f99-275">Property</span></span>|<span data-ttu-id="14f99-276">値</span><span class="sxs-lookup"><span data-stu-id="14f99-276">Value(s)</span></span>|<span data-ttu-id="14f99-277">既定値</span><span class="sxs-lookup"><span data-stu-id="14f99-277">Default Value</span></span>|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|<span data-ttu-id="14f99-278">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="14f99-278">Numeric value - byte</span></span>|<span data-ttu-id="14f99-279">0</span><span class="sxs-lookup"><span data-stu-id="14f99-279">0</span></span>|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<span data-ttu-id="14f99-280"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span><span class="sxs-lookup"><span data-stu-id="14f99-280"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span></span>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|<span data-ttu-id="14f99-281">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="14f99-281">Numeric value - byte</span></span>|<span data-ttu-id="14f99-282">0</span><span class="sxs-lookup"><span data-stu-id="14f99-282">0</span></span>|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<span data-ttu-id="14f99-283"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span><span class="sxs-lookup"><span data-stu-id="14f99-283"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span></span>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<span data-ttu-id="14f99-284"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span><span class="sxs-lookup"><span data-stu-id="14f99-284"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span></span>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<span data-ttu-id="14f99-285"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span><span class="sxs-lookup"><span data-stu-id="14f99-285"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span></span>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<span data-ttu-id="14f99-286"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span><span class="sxs-lookup"><span data-stu-id="14f99-286"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span></span>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|<span data-ttu-id="14f99-287">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="14f99-287">numeric value – byte</span></span>|<span data-ttu-id="14f99-288">0</span><span class="sxs-lookup"><span data-stu-id="14f99-288">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|<span data-ttu-id="14f99-289">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="14f99-289">numeric value – byte</span></span>|<span data-ttu-id="14f99-290">0</span><span class="sxs-lookup"><span data-stu-id="14f99-290">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<span data-ttu-id="14f99-291"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span><span class="sxs-lookup"><span data-stu-id="14f99-291"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span></span>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="14f99-292">関連項目</span><span class="sxs-lookup"><span data-stu-id="14f99-292">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- [<span data-ttu-id="14f99-293">OpenType 仕様</span><span class="sxs-lookup"><span data-stu-id="14f99-293">OpenType specification</span></span>](/typography/opentype/spec/)
- [<span data-ttu-id="14f99-294">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="14f99-294">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="14f99-295">OpenType フォント パックのサンプル</span><span class="sxs-lookup"><span data-stu-id="14f99-295">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
- [<span data-ttu-id="14f99-296">アプリケーションでのフォントのパッケージング</span><span class="sxs-lookup"><span data-stu-id="14f99-296">Packaging Fonts with Applications</span></span>](packaging-fonts-with-applications.md)
