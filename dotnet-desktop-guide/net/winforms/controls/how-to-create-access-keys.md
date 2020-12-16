---
title: コントロールのアクセス キーを作成する
description: .NET 用の Windows フォームでコントロールまたはラベルにアクセス キーのショートカットを設定する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.openlocfilehash: 4d746082ffbaa749b882dcb1a769b5f9541c6fe8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942346"
---
# <a name="add-an-access-key-shortcut-to-a-control-windows-forms-net"></a><span data-ttu-id="96658-103">コントロールにアクセス キーのショートカットを追加する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="96658-103">Add an access key shortcut to a control (Windows Forms .NET)</span></span>

<span data-ttu-id="96658-104">"*アクセス キー*" は、メニュー、メニュー項目、またはボタンなどのコントロールのラベルのテキスト内の下線付きの文字です。</span><span class="sxs-lookup"><span data-stu-id="96658-104">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="96658-105">アクセス キーを使用すると、ユーザーは <kbd>Alt</kbd> キーを定義済みのアクセス キーと組み合わせて押すことで、ボタンを "クリック" できます。</span><span class="sxs-lookup"><span data-stu-id="96658-105">With an access key, the user can "click" a button by pressing the <kbd>Alt</kbd> key in combination with the predefined access key.</span></span> <span data-ttu-id="96658-106">たとえば、ボタンがフォームを印刷するプロシージャを実行することから、その `Text` プロパティが "Print" に設定されている場合、文字 "P" の前にアンパサンド (&) を追加すると、実行時にボタンのテキスト内の文字 "P" が下線付きで表示されます。</span><span class="sxs-lookup"><span data-stu-id="96658-106">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="96658-107">ユーザーは <kbd>Alt</kbd> キーを押すことで、ボタンに関連付けられているコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96658-107">The user can run the command associated with the button by pressing <kbd>Alt</kbd>.</span></span>

<span data-ttu-id="96658-108">フォーカスを受け取ることができないコントロールは、ラベル コントロールを除いてアクセス キーを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="96658-108">Controls that cannot receive focus can't have access keys, except label controls.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="96658-109">Designer</span><span class="sxs-lookup"><span data-stu-id="96658-109">Designer</span></span>

<span data-ttu-id="96658-110">Visual Studio の **[プロパティ]** ウィンドウで、**Text** プロパティを、アクセス キーにする文字の前にアンパサンド (&) を含む文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="96658-110">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="96658-111">たとえば、文字 "P" をアクセス キーとして設定するには、「 **&Print**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="96658-111">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

:::image type="content" source="media/how-to-create-access-keys/properties-text.png" alt-text="Text プロパティが選択されアクセス キーが表示された [プロパティ] ダイアログ":::

## <a name="programmatic"></a><span data-ttu-id="96658-113">プログラムによる</span><span class="sxs-lookup"><span data-stu-id="96658-113">Programmatic</span></span>

<span data-ttu-id="96658-114">`Text` プロパティを、ショートカットにする文字の前にアンパサンド (&) を含む文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="96658-114">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

## <a name="use-a-label-to-focus-a-control"></a><span data-ttu-id="96658-115">ラベルを使用してコントロールにフォーカスを設定する</span><span class="sxs-lookup"><span data-stu-id="96658-115">Use a label to focus a control</span></span>

<span data-ttu-id="96658-116">ラベルにフォーカスを設定することはできませんが、フォームのタブ オーダーで次のコントロールにフォーカスを設定する機能があります。</span><span class="sxs-lookup"><span data-stu-id="96658-116">Even though a label cannot be focused, it has the ability to focus the next control in the tab order of the form.</span></span> <span data-ttu-id="96658-117">各コントロールには、<xref:System.Windows.Forms.Control.TabIndex> プロパティの値が (通常は昇順で) 割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="96658-117">Each control is assigned a value to the <xref:System.Windows.Forms.Control.TabIndex> property, generally in ascending sequential order.</span></span> <span data-ttu-id="96658-118">アクセス キーが [Label.Text](xref:System.Windows.Forms.Label.Text) プロパティに割り当てられている場合、タブ オーダーで次のコントロールにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="96658-118">When the access key is assigned to the [Label.Text](xref:System.Windows.Forms.Label.Text) property, the next control in the sequential tab order is focused.</span></span>

<span data-ttu-id="96658-119">「[プログラムによる](#programmatic)」セクションの例を使用すると、ボタンに何もテキストが設定されておらず、代わりにプリンターの画像が表示されていた場合は、ラベルを使用してボタンにフォーカスを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="96658-119">Using the example from the [Programmatic](#programmatic) section, if the button didn't have any text set, but instead presented an image of a printer, you could use a label to focus the button.</span></span>

```vb
' Set the letter "P" as an access key.
Label1.Text = "&Print"
Label1.TabIndex = 9
Button1.TabIndex = 10
```

```csharp
// Set the letter "P" as an access key.
label1.Text = "&Print";
label1.TabIndex = 9
button1.TabIndex = 10
```

## <a name="display-an-ampersand"></a><span data-ttu-id="96658-120">アンパサンドを表示する</span><span class="sxs-lookup"><span data-stu-id="96658-120">Display an ampersand</span></span>

<span data-ttu-id="96658-121">アンパサンド (&) をアクセス キーとして解釈するコントロールのテキストまたはキャプションを設定する場合は、2 つの連続するアンパサンド (&&) を使用して、1 つのアンパサンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="96658-121">When setting the text or caption of a control that interprets an ampersand (&) as an access key, use two consecutive ampersands (&&) to display a single ampersand.</span></span> <span data-ttu-id="96658-122">たとえば、`"Print && Close"` に設定されたボタンのテキストは、`Print & Close` のキャプションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="96658-122">For example, the text of a button set to `"Print && Close"` displays in the caption of `Print & Close`:</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "Print && Close"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "Print && Close";
```

:::image type="content" source="media/how-to-create-access-keys/double-ampersand.png" alt-text="ボタンにアンパサンドを表示する":::

## <a name="see-also"></a><span data-ttu-id="96658-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="96658-124">See also</span></span>

- [<span data-ttu-id="96658-125">方法: Windows フォーム コントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="96658-125">How to: Set the text displayed by a Windows Forms control</span></span>](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.Label>
