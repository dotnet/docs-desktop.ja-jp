---
title: '方法: コンテキスト メニューでスペル チェックを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 0c2ceb3e4091ee1d98bd0c786f51b3596cdedd08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974661"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="bb975-102">方法: コンテキスト メニューでスペル チェックを使用する</span><span class="sxs-lookup"><span data-stu-id="bb975-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="bb975-103">既定では、<xref:System.Windows.Controls.TextBox> や <xref:System.Windows.Controls.RichTextBox> のような編集コントロールでスペルチェックを有効にすると、コンテキスト メニューにスペルチェックの選択肢が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb975-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="bb975-104">たとえば、綴りが間違っている単語をユーザーがクリックすると、綴り案がひととおり表示されるか、 **[すべて無視]** オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb975-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="bb975-105">ただし、既定のコンテキスト メニューを独自のコンテキスト メニューでオーバーライドすると、この機能は失われます。コンテキスト メニューでスペルチェック機能を再び有効にするコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb975-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="bb975-106">次の例では、<xref:System.Windows.Controls.TextBox> でこれを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bb975-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb975-107">例</span><span class="sxs-lookup"><span data-stu-id="bb975-107">Example</span></span>  
 <span data-ttu-id="bb975-108">次の例では、コンテキスト メニューの実装に使用されるイベントをいくつか含む <xref:System.Windows.Controls.TextBox> を作成する [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を示します。</span><span class="sxs-lookup"><span data-stu-id="bb975-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="bb975-109">例</span><span class="sxs-lookup"><span data-stu-id="bb975-109">Example</span></span>  
 <span data-ttu-id="bb975-110">次の例では、コンテキスト メニューを実装するコードを示します。</span><span class="sxs-lookup"><span data-stu-id="bb975-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="bb975-111"><xref:System.Windows.Controls.RichTextBox> でこれを行うためのコードも似ています。</span><span class="sxs-lookup"><span data-stu-id="bb975-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="bb975-112">主な違いは、`GetSpellingError` メソッドに渡されるパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="bb975-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="bb975-113"><xref:System.Windows.Controls.TextBox> の場合、カーソル位置の整数インデックスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="bb975-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="bb975-114"><xref:System.Windows.Controls.RichTextBox> の場合、キャレット位置を指定する <xref:System.Windows.Documents.TextPointer> が渡されます。</span><span class="sxs-lookup"><span data-stu-id="bb975-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="bb975-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb975-115">See also</span></span>

- [<span data-ttu-id="bb975-116">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="bb975-116">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="bb975-117">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="bb975-117">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="bb975-118">テキスト編集コントロールでスペル チェックを有効にする</span><span class="sxs-lookup"><span data-stu-id="bb975-118">Enable Spell Checking in a Text Editing Control</span></span>](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="bb975-119">TextBox でカスタム コンテキスト メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="bb975-119">Use a Custom Context Menu with a TextBox</span></span>](how-to-use-a-custom-context-menu-with-a-textbox.md)
