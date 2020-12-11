---
title: '方法: テキストのトリミングを有効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984612"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="3497c-102">方法: テキストのトリミングを有効にする</span><span class="sxs-lookup"><span data-stu-id="3497c-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="3497c-103">この例では、<xref:System.Windows.TextTrimming> 列挙型で使用可能な値の使用方法と効果を示します。</span><span class="sxs-lookup"><span data-stu-id="3497c-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="3497c-104">例</span><span class="sxs-lookup"><span data-stu-id="3497c-104">Example</span></span>

<span data-ttu-id="3497c-105">次の例では、<xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 属性セットを使用して <xref:System.Windows.Controls.TextBlock> 要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="3497c-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="3497c-106">コード内で対応する <xref:System.Windows.TextTrimming> プロパティを設定する方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3497c-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="3497c-107">現在、テキストのトリミングには次の 3 つのオプションがあります: **CharacterEllipsis**、**WordEllipsis**、**None**。</span><span class="sxs-lookup"><span data-stu-id="3497c-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="3497c-108"><xref:System.Windows.Controls.TextBlock.TextTrimming%2A> を **CharacterEllipsis** に設定した場合、テキストがトリミングされ、トリミング エッジに最も近い文字の位置に省略記号が続きます。</span><span class="sxs-lookup"><span data-stu-id="3497c-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="3497c-109">この設定では、トリミング境界により近い位置でテキストが切り取られます。ただし、単語の一部が切り取られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3497c-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="3497c-110">次の図は、上記で定義したものと同様の <xref:System.Windows.Controls.TextBlock> におけるこの設定の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="3497c-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="3497c-111">![例: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="3497c-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="3497c-112"><xref:System.Windows.Controls.TextBlock.TextTrimming%2A> を **WordEllipsis** に設定した場合、テキストがトリミングされ、トリミング エッジに最も近い位置にある最初の完全な単語の後に省略記号が続きます。</span><span class="sxs-lookup"><span data-stu-id="3497c-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="3497c-113">この設定では、部分的にトリミングされた単語は表示されませんが、**CharacterEllipsis** 設定よりもトリミング エッジから離れた位置でテキストがトリミングされる傾向にあります。</span><span class="sxs-lookup"><span data-stu-id="3497c-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="3497c-114">次の図は、上記で定義された <xref:System.Windows.Controls.TextBlock> のこの設定の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="3497c-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="3497c-115">![例 : TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="3497c-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="3497c-116"><xref:System.Windows.Controls.TextBlock.TextTrimming%2A> が **None** に設定されている場合、テキストのトリミングは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3497c-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="3497c-117">この場合、テキストは親テキスト コンテナーの境界にトリミングされるだけです。</span><span class="sxs-lookup"><span data-stu-id="3497c-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="3497c-118">次の図は、上記で定義したものと同様の <xref:System.Windows.Controls.TextBlock> におけるこの設定の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="3497c-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="3497c-119">![例 : TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="3497c-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
