---
title: RichTextBox の概要
description: Windows Presentation Foundation RichTextBox コントロールを使用して、ユーザーがテキスト、画像、テーブルなどのコンテンツをどのように表示または編集できるかを説明します。 XAML と C# の例を参照してください。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 2d32c5ab2647f984d7677125fb146adede62abc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985311"
---
# <a name="richtextbox-overview"></a><span data-ttu-id="31677-104">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="31677-104">RichTextBox Overview</span></span>

<span data-ttu-id="31677-105"><xref:System.Windows.Controls.RichTextBox> コントロールでは、段落、イメージ、テーブルなどのフロー コンテンツを表示または編集できます。</span><span class="sxs-lookup"><span data-stu-id="31677-105">The <xref:System.Windows.Controls.RichTextBox> control enables you to display or edit flow content including paragraphs, images, tables, and more.</span></span> <span data-ttu-id="31677-106">このトピックでは、<xref:System.Windows.Controls.TextBox> クラスを紹介し、それを [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] と C# の両方で使用する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="31677-106">This topic introduces the <xref:System.Windows.Controls.TextBox> class and provides examples of how to use it in both [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] and C#.</span></span>

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a><span data-ttu-id="31677-107">TextBox か RichTextBox か</span><span class="sxs-lookup"><span data-stu-id="31677-107">TextBox or RichTextBox?</span></span>

<span data-ttu-id="31677-108"><xref:System.Windows.Controls.RichTextBox> と <xref:System.Windows.Controls.TextBox> の両方で、ユーザーはテキストを編集できますが、2 つのコントロールは異なるシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="31677-108">Both <xref:System.Windows.Controls.RichTextBox> and <xref:System.Windows.Controls.TextBox> allow users to edit text, however, the two controls are used in different scenarios.</span></span> <span data-ttu-id="31677-109"><xref:System.Windows.Controls.RichTextBox> は、ユーザーが書式設定されたテキスト、イメージ、テーブル、またはその他のリッチ コンテンツを編集する必要がある場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="31677-109">A <xref:System.Windows.Controls.RichTextBox> is a better choice when it is necessary for the user to edit formatted text, images, tables, or other rich content.</span></span> <span data-ttu-id="31677-110">たとえば、書式設定やイメージなどを必要とするドキュメント、記事、またはブログを編集する場合は、<xref:System.Windows.Controls.RichTextBox> を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31677-110">For example, editing a document, article, or blog that requires formatting, images, etc is best accomplished using a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="31677-111"><xref:System.Windows.Controls.TextBox> で必要なシステム リソースは、<xref:System.Windows.Controls.RichTextBox> よりも少なく、プレーン テキストのみを編集する必要がある場合 (つまり、フォームでの使用) に最適です。</span><span class="sxs-lookup"><span data-stu-id="31677-111">A <xref:System.Windows.Controls.TextBox> requires less system resources then a <xref:System.Windows.Controls.RichTextBox> and it is ideal when only plain text needs to be edited (i.e. usage in forms).</span></span> <span data-ttu-id="31677-112"><xref:System.Windows.Controls.TextBox> の詳細については、「[TextBox の概要](textbox-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-112">See [TextBox Overview](textbox-overview.md) for more information on <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="31677-113">次の表は、<xref:System.Windows.Controls.TextBox> と <xref:System.Windows.Controls.RichTextBox> の主な機能をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="31677-113">The table below summarizes the main features of <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox>.</span></span>

|<span data-ttu-id="31677-114">Control</span><span class="sxs-lookup"><span data-stu-id="31677-114">Control</span></span>|<span data-ttu-id="31677-115">リアルタイム スペル チェック</span><span class="sxs-lookup"><span data-stu-id="31677-115">Real-time Spellchecking</span></span>|<span data-ttu-id="31677-116">コンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="31677-116">Context Menu</span></span>|<span data-ttu-id="31677-117"><xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B) のような書式設定コマンド</span><span class="sxs-lookup"><span data-stu-id="31677-117">Formatting commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B)</span></span>|<span data-ttu-id="31677-118">イメージ、段落、テーブルのような <xref:System.Windows.Documents.FlowDocument> コンテンツ</span><span class="sxs-lookup"><span data-stu-id="31677-118"><xref:System.Windows.Documents.FlowDocument> content like images, paragraphs, tables, etc.</span></span>|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="31677-119">はい</span><span class="sxs-lookup"><span data-stu-id="31677-119">Yes</span></span>|<span data-ttu-id="31677-120">[はい]</span><span class="sxs-lookup"><span data-stu-id="31677-120">Yes</span></span>|<span data-ttu-id="31677-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="31677-121">No</span></span>|<span data-ttu-id="31677-122">いいえ。</span><span class="sxs-lookup"><span data-stu-id="31677-122">No.</span></span>|
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="31677-123">はい</span><span class="sxs-lookup"><span data-stu-id="31677-123">Yes</span></span>|<span data-ttu-id="31677-124">はい</span><span class="sxs-lookup"><span data-stu-id="31677-124">Yes</span></span>|<span data-ttu-id="31677-125">○</span><span class="sxs-lookup"><span data-stu-id="31677-125">Yes</span></span>|<span data-ttu-id="31677-126">はい</span><span class="sxs-lookup"><span data-stu-id="31677-126">Yes</span></span>|

> [!NOTE]
> <span data-ttu-id="31677-127"><xref:System.Windows.Controls.TextBox> では <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B) のような書式設定関連のコマンドはサポートされませんが、<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> などの多くの基本的なコマンドは両方のコントロールでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="31677-127">Although <xref:System.Windows.Controls.TextBox> does not support formatting related commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B), many basic commands are supported by both controls such as <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.</span></span>

<span data-ttu-id="31677-128">上の表の機能については、後で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="31677-128">The features from the table above are covered in more detail later.</span></span>

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a><span data-ttu-id="31677-129">RichTextBox の作成</span><span class="sxs-lookup"><span data-stu-id="31677-129">Creating a RichTextBox</span></span>

<span data-ttu-id="31677-130">以下のコードには、ユーザーがリッチ コンテンツを編集できる <xref:System.Windows.Controls.RichTextBox> を作成する方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="31677-130">The code below shows how to create a <xref:System.Windows.Controls.RichTextBox> that a user can edit rich content in.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

<span data-ttu-id="31677-131">具体的には、<xref:System.Windows.Controls.RichTextBox> で編集されるコンテンツはフロー コンテンツです。</span><span class="sxs-lookup"><span data-stu-id="31677-131">Specifically, the content edited in a <xref:System.Windows.Controls.RichTextBox> is flow content.</span></span> <span data-ttu-id="31677-132">フロー コンテンツは、書式設定されたテキスト、イメージ、リスト、テーブルなどのさまざまな種類の要素を格納できます。</span><span class="sxs-lookup"><span data-stu-id="31677-132">Flow content can contain many types of elements including formatted text, images, lists, and tables.</span></span> <span data-ttu-id="31677-133">フロー ドキュメントの詳細については、[フロー ドキュメントの概要](../advanced/flow-document-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-133">See [Flow Document Overview](../advanced/flow-document-overview.md) for in depth information on flow documents.</span></span> <span data-ttu-id="31677-134">フロー コンテンツを含めるために、<xref:System.Windows.Controls.RichTextBox> では <xref:System.Windows.Documents.FlowDocument> オブジェクトがホストされ、次にそれには編集可能なコンテンツが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31677-134">In order to contain flow content, a <xref:System.Windows.Controls.RichTextBox> hosts a <xref:System.Windows.Documents.FlowDocument> object which in turn contains the editable content.</span></span> <span data-ttu-id="31677-135"><xref:System.Windows.Controls.RichTextBox> のフロー コンテンツを示すために、次のコードでは、段落と何らかの太字のテキストを使用して <xref:System.Windows.Controls.RichTextBox> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="31677-135">To demonstrate flow content in a <xref:System.Windows.Controls.RichTextBox>, the following code shows how to create a <xref:System.Windows.Controls.RichTextBox> with a paragraph and some bolded text.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

<span data-ttu-id="31677-136">次の図は、このサンプルがレンダリングする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31677-136">The following illustration shows how this sample renders.</span></span>

<span data-ttu-id="31677-137">![コンテンツを含む RichTextBox](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span><span class="sxs-lookup"><span data-stu-id="31677-137">![RichTextBox with content](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span></span>

<span data-ttu-id="31677-138"><xref:System.Windows.Documents.Paragraph> や <xref:System.Windows.Documents.Bold> などの要素で、<xref:System.Windows.Controls.RichTextBox> 内のコンテンツがどのように表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="31677-138">Elements like <xref:System.Windows.Documents.Paragraph> and <xref:System.Windows.Documents.Bold> determine how the content inside a <xref:System.Windows.Controls.RichTextBox> appears.</span></span> <span data-ttu-id="31677-139">ユーザーが <xref:System.Windows.Controls.RichTextBox> コンテンツを編集すると、このフロー コンテンツが変更されます。</span><span class="sxs-lookup"><span data-stu-id="31677-139">As a user edits <xref:System.Windows.Controls.RichTextBox> content, they change this flow content.</span></span> <span data-ttu-id="31677-140">フロー コンテンツの機能およびその操作方法の詳細については、[フロー ドキュメントの概要](../advanced/flow-document-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-140">To learn more about the features of flow content and how to work with it, see [Flow Document Overview](../advanced/flow-document-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="31677-141"><xref:System.Windows.Controls.RichTextBox> 内のフロー コンテンツは、他のコントロールに含まれているフロー コンテンツと一部異なる動作をします。</span><span class="sxs-lookup"><span data-stu-id="31677-141">Flow content inside a <xref:System.Windows.Controls.RichTextBox> does not behave exactly like flow content contained in other controls.</span></span> <span data-ttu-id="31677-142">たとえば、<xref:System.Windows.Controls.RichTextBox> に列がないと、自動サイズ変更動作は行われません。</span><span class="sxs-lookup"><span data-stu-id="31677-142">For example, there are no columns in a <xref:System.Windows.Controls.RichTextBox> and hence no automatic resizing behavior.</span></span> <span data-ttu-id="31677-143">また、検索、表示モード、ページ ナビゲーション、ズームなどの組み込み機能は、<xref:System.Windows.Controls.RichTextBox> 内では利用できません。</span><span class="sxs-lookup"><span data-stu-id="31677-143">Also, built in features like search, viewing mode, page navigation, and zoom are not available within a <xref:System.Windows.Controls.RichTextBox>.</span></span>

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a><span data-ttu-id="31677-144">リアルタイム スペル チェック</span><span class="sxs-lookup"><span data-stu-id="31677-144">Real-time Spell Checking</span></span>

<span data-ttu-id="31677-145"><xref:System.Windows.Controls.TextBox> または <xref:System.Windows.Controls.RichTextBox> で、リアルタイム スペル チェックを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="31677-145">You can enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="31677-146">スペル チェックをオンにすると、スペル ミスの語句の下に赤色の線が表示されます (下図を参照)。</span><span class="sxs-lookup"><span data-stu-id="31677-146">When spellchecking is turned on, a red line appears underneath any misspelled words (see picture below).</span></span>

<span data-ttu-id="31677-147">![スペル チェックを含む TextBox](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span><span class="sxs-lookup"><span data-stu-id="31677-147">![Textbox with spell&#45;checking](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span></span>

<span data-ttu-id="31677-148">スペル チェックを有効にする方法については、「[テキスト編集コントロールでスペル チェックを有効にする](how-to-enable-spell-checking-in-a-text-editing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-148">See [Enable Spell Checking in a Text Editing Control](how-to-enable-spell-checking-in-a-text-editing-control.md) to learn how to enable spellchecking.</span></span>

<a name="context_menu"></a>

## <a name="context-menu"></a><span data-ttu-id="31677-149">コンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="31677-149">Context Menu</span></span>

<span data-ttu-id="31677-150">既定では、<xref:System.Windows.Controls.TextBox> と <xref:System.Windows.Controls.RichTextBox> の両方に、ユーザーがコントロール内を右クリックしたときに表示されるコンテキスト メニューがあります。</span><span class="sxs-lookup"><span data-stu-id="31677-150">By default, both <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox> have a context menu that appears when a user right-clicks inside the control.</span></span> <span data-ttu-id="31677-151">コンテキスト メニューでは、ユーザーは、切り取り、コピー、または貼り付けをできます (下図を参照)。</span><span class="sxs-lookup"><span data-stu-id="31677-151">The context menu allows the user to cut, copy, or paste (see illustration below).</span></span>

<span data-ttu-id="31677-152">![コンテキスト メニューを含む TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span><span class="sxs-lookup"><span data-stu-id="31677-152">![TextBox with context menu](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span></span>

<span data-ttu-id="31677-153">独自のカスタム コンテキスト メニューを作成して、既定のコンテキスト メニューをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="31677-153">You can create your own custom context menu to override the default one.</span></span> <span data-ttu-id="31677-154">詳細については、[カスタム コンテキスト メニューを RichTextBox に配置](how-to-position-a-custom-context-menu-in-a-richtextbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-154">See [Position a Custom Context Menu in a RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md) for more information.</span></span>

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a><span data-ttu-id="31677-155">コマンドの編集</span><span class="sxs-lookup"><span data-stu-id="31677-155">Editing Commands</span></span>

<span data-ttu-id="31677-156">コマンドの編集では、ユーザーは、<xref:System.Windows.Controls.RichTextBox> 内の編集可能なコンテンツの書式を設定できます。</span><span class="sxs-lookup"><span data-stu-id="31677-156">Editing commands enable users to format editable content inside a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="31677-157"><xref:System.Windows.Controls.RichTextBox> には、基本的な編集コマンドのほかに、<xref:System.Windows.Controls.TextBox> ではサポートされない書式設定コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31677-157">Besides basic editing commands, <xref:System.Windows.Controls.RichTextBox> includes formatting commands that <xref:System.Windows.Controls.TextBox> does not support.</span></span> <span data-ttu-id="31677-158">たとえば、<xref:System.Windows.Controls.RichTextBox> で編集する場合、ユーザーは、Ctr + B キーを押して太字テキストの書式設定を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="31677-158">For example, when editing in a <xref:System.Windows.Controls.RichTextBox>, a user could press Ctr+B to toggle bold text formatting.</span></span> <span data-ttu-id="31677-159">使用できるコマンドの完全な一覧については、「<xref:System.Windows.Documents.EditingCommands>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-159">See <xref:System.Windows.Documents.EditingCommands> for a complete list of commands available.</span></span> <span data-ttu-id="31677-160">キーボード ショートカットを使用するだけでなく、ボタンのようにコマンドをフックしてその他のコントロールにすることができます。</span><span class="sxs-lookup"><span data-stu-id="31677-160">In addition to using keyboard shortcuts, you can hook commands up to other controls like buttons.</span></span> <span data-ttu-id="31677-161">次の例では、テキストの書式設定を変更するためにユーザーが使用できるボタンを含む簡単なツールバーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="31677-161">The following example shows how to create a simple tool bar containing buttons that the user can use to change text formatting.</span></span>

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

<span data-ttu-id="31677-162">次の図は、このサンプルの表示方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31677-162">The following illustration shows how this sample displays.</span></span>

<span data-ttu-id="31677-163">![ツール バーを含む RichTextBox](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span><span class="sxs-lookup"><span data-stu-id="31677-163">![RichTextBox with ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span></span>

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a><span data-ttu-id="31677-164">コンテンツがいつ変更されたかの検出</span><span class="sxs-lookup"><span data-stu-id="31677-164">Detect when Content Changes</span></span>

<span data-ttu-id="31677-165">通常、<xref:System.Windows.Controls.TextBox> または <xref:System.Windows.Controls.RichTextBox> のテキストが変更されたときには常に、予想どおり、<xref:System.Windows.UIElement.KeyDown> ではなく、<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> イベントを使用して検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31677-165">Usually the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event should be used to detect whenever the text in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox> changes rather then <xref:System.Windows.UIElement.KeyDown> as you might expect.</span></span> <span data-ttu-id="31677-166">例については、「[TextBox のテキストがいつ変更されたかを検出する](how-to-detect-when-text-in-a-textbox-has-changed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31677-166">See [Detect When Text in a TextBox Has Changed](how-to-detect-when-text-in-a-textbox-has-changed.md) for an example.</span></span>

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a><span data-ttu-id="31677-167">RichTextBox コンテンツの保存、読み込み、および印刷</span><span class="sxs-lookup"><span data-stu-id="31677-167">Save, Load, and Print RichTextBox Content</span></span>

<span data-ttu-id="31677-168">次の例では、<xref:System.Windows.Controls.RichTextBox> のコンテンツをファイルに保存し、そのコンテンツを <xref:System.Windows.Controls.RichTextBox> に再度読み込み、コンテンツを印刷する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="31677-168">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span> <span data-ttu-id="31677-169">この例のマークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31677-169">Below is the markup for the example.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

<span data-ttu-id="31677-170">この例のコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31677-170">Below is the code behind for the example.</span></span>

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="31677-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="31677-171">See also</span></span>

- [<span data-ttu-id="31677-172">方法トピック</span><span class="sxs-lookup"><span data-stu-id="31677-172">How-to Topics</span></span>](richtextbox-how-to-topics.md)
- [<span data-ttu-id="31677-173">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="31677-173">TextBox Overview</span></span>](textbox-overview.md)
