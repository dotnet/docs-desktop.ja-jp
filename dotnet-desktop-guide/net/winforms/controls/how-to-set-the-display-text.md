---
title: コントロールによって表示されるテキストを設定する
description: Windows フォーム コントロールによって表示されるテキストを設定する方法について説明します。 テキストを設定する、または返すには、Text プロパティを使用します。また、フォントを変更するには、Font プロパティを使用します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.openlocfilehash: 2fd5a62310ae5e7d6e0528c7f12f37ed40f8a626
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942194"
---
# <a name="how-to-set-the-text-displayed-by-a-control-windows-forms-net"></a><span data-ttu-id="435e2-104">方法:コントロールによって表示されるテキストを設定する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="435e2-104">How to: Set the text displayed by a control (Windows Forms .NET)</span></span>

<span data-ttu-id="435e2-105">Windows フォーム コントロールは、通常、コントロールの主な機能に関連するいくつかのテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="435e2-105">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="435e2-106">たとえば、<xref:System.Windows.Forms.Button> コントロールは、通常、ボタンがクリックされたときにどのようなアクションを実行するかを示すキャプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="435e2-106">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="435e2-107">すべてのコントロールに対して、<xref:System.Windows.Forms.Control.Text%2A> プロパティを使用してテキストを設定または返すことができます。</span><span class="sxs-lookup"><span data-stu-id="435e2-107">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="435e2-108"><xref:System.Windows.Forms.Control.Font%2A> プロパティを使用して、フォントを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="435e2-108">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="435e2-109">また、[デザイナー](#designer)を使用してテキストを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="435e2-109">You can also set the text by using the [designer](#designer).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="435e2-110">Designer</span><span class="sxs-lookup"><span data-stu-id="435e2-110">Designer</span></span>

01. <span data-ttu-id="435e2-111">Visual Studio の **プロパティ** ウィンドウで、コントロールの **Text** プロパティを適切な文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="435e2-111">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

    <span data-ttu-id="435e2-112">下線付きのショートカット キーを作成するには、ショートカット キーとなる文字の前にアンパサンド (&) を含めます。</span><span class="sxs-lookup"><span data-stu-id="435e2-112">To create an underlined shortcut key, include an ampersand (&) before the letter that will be the shortcut key.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-text.png" alt-text=".NET Windows フォームの Text プロパティが表示された Visual Studio の [プロパティ] ペイン。":::

01. <span data-ttu-id="435e2-114">**プロパティ** ウィンドウで、**Font** プロパティの横にある省略記号ボタン (![Visual Studio のプロパティ ウィンドウの省略記号ボタン (...)](../media/visual-studio-ellipsis-button.png)) を選択します。</span><span class="sxs-lookup"><span data-stu-id="435e2-114">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](../media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-font.png" alt-text=".NET Windows フォームの Font プロパティが表示された Visual Studio の [プロパティ] ペイン。":::

    <span data-ttu-id="435e2-116">標準フォント ダイアログボックスで、種類、サイズ、スタイルなどの設定を使用してフォントを調整します。</span><span class="sxs-lookup"><span data-stu-id="435e2-116">In the standard font dialog box, adjust the font with settings such as type, size, and style.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/font-window.png" alt-text=".NET Windows フォームの [フォント] 設定ウィンドウが表示された Visual Studio の [プロパティ] ペイン。":::

## <a name="programmatic"></a><span data-ttu-id="435e2-118">プログラムによる</span><span class="sxs-lookup"><span data-stu-id="435e2-118">Programmatic</span></span>

01. <span data-ttu-id="435e2-119"><xref:System.Windows.Forms.Control.Text%2A> プロパティを文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="435e2-119">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

    <span data-ttu-id="435e2-120">下線付きのアクセス キーを作成するには、アクセス キーにする文字の前にアンパサンド (&) を含めます。</span><span class="sxs-lookup"><span data-stu-id="435e2-120">To create an underlined access key, include an ampersand (&) before the letter that will be the access key.</span></span>

01. <span data-ttu-id="435e2-121"><xref:System.Windows.Forms.Control.Font%2A> プロパティを型 <xref:System.Drawing.Font> のオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="435e2-121">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="435e2-122">エスケープ文字を使用すると、メニュー項目など、通常は別の解釈がなされるユーザー インターフェイス要素の特殊文字を表示できます。</span><span class="sxs-lookup"><span data-stu-id="435e2-122">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="435e2-123">たとえば、次のコード行は、メニュー項目のテキストが "& Now For Something Completely Different" と読めるように設定します。</span><span class="sxs-lookup"><span data-stu-id="435e2-123">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

## <a name="see-also"></a><span data-ttu-id="435e2-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="435e2-124">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="435e2-125">方法 : Windows フォーム コントロールのアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="435e2-125">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys.md)
