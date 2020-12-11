---
title: '方法: TextBox へのウォーターマークの追加'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983608"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="6cfe8-102">方法: TextBox へのウォーターマークの追加</span><span class="sxs-lookup"><span data-stu-id="6cfe8-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="6cfe8-103">次の例では、<xref:System.Windows.Controls.TextBox> 内に説明のための背景画像を表示し、ユーザーがテキストを入力すると消えるようにすることで、<xref:System.Windows.Controls.TextBox> の利便性を向上させる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6cfe8-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="6cfe8-104">また、ユーザーが入力を削除すると、背景画像が再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cfe8-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="6cfe8-105">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cfe8-105">See illustration below.</span></span>  
  
 <span data-ttu-id="6cfe8-106">![背景イメージを含む TextBox](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="6cfe8-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cfe8-107">この例で、<xref:System.Windows.Controls.TextBox> の <xref:System.Windows.Controls.TextBox.Text%2A> プロパティを操作するのではなく、背景画像が使用されているのは、背景画像がデータ バインディングに干渉しないという理由からです。</span><span class="sxs-lookup"><span data-stu-id="6cfe8-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cfe8-108">例</span><span class="sxs-lookup"><span data-stu-id="6cfe8-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6cfe8-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cfe8-109">See also</span></span>

- [<span data-ttu-id="6cfe8-110">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="6cfe8-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="6cfe8-111">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="6cfe8-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
