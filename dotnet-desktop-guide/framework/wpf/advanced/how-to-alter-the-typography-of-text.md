---
title: 方法:テキストの文字体裁を変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: 4c027424632f8671ba8d7cae1c899ef3a53edc26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982308"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="1d15f-102">方法:テキストの文字体裁を変更する</span><span class="sxs-lookup"><span data-stu-id="1d15f-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="1d15f-103">次の例では、<xref:System.Windows.Documents.Paragraph> を例の要素として使用して、<xref:System.Windows.Documents.TextElement.Typography%2A> 属性を設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1d15f-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d15f-104">例</span><span class="sxs-lookup"><span data-stu-id="1d15f-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="1d15f-105">この例の表示結果を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1d15f-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="1d15f-106">![スクリーンショット: 変更されたタイポグラフィを含むテキスト](./media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="1d15f-106">![Screenshot: Text with altered typography](./media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="1d15f-107">これに対し、既定の文字体裁プロパティを設定した同様の例がどのように表示されるかを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1d15f-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="1d15f-108">![スクリーンショット: 変更されたタイポグラフィを含むテキスト](./media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="1d15f-108">![Screenshot: Text with altered typography](./media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d15f-109">例</span><span class="sxs-lookup"><span data-stu-id="1d15f-109">Example</span></span>  
 <span data-ttu-id="1d15f-110">次の例では、<xref:System.Windows.Controls.TextBox.Typography%2A> プロパティをプログラムで設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1d15f-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="1d15f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d15f-111">See also</span></span>

- [<span data-ttu-id="1d15f-112">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="1d15f-112">Flow Document Overview</span></span>](flow-document-overview.md)
