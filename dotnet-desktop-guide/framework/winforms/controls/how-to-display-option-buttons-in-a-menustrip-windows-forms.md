---
title: '方法: MenuStrip にオプション ボタンを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982555"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="6e6ad-102">方法 : MenuStrip にオプション ボタンを表示する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="6e6ad-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="6e6ad-103">オプションボタンは、オプションボタンとも呼ばれ、ユーザーが一度に1つだけ選択できる点を除いて、チェックボックスに似ています。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="6e6ad-104">既定では、 <xref:System.Windows.Forms.ToolStripMenuItem> クラスにはオプションボタンの動作が用意されていませんが、クラスには、コントロールのメニュー項目に対してオプションボタンの動作を実装するようにカスタマイズできるチェックボックスの動作が用意されてい <xref:System.Windows.Forms.MenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="6e6ad-105"><xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>メニュー項目のプロパティがの場合 `true` 、ユーザーは項目をクリックしてチェックマークの表示を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="6e6ad-106">プロパティは、 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 項目の現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="6e6ad-107">基本的なオプションボタンの動作を実装するには、項目が選択されているときに、前に選択した項目のプロパティをに設定する必要があり <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="6e6ad-108">次の手順では、クラスを継承するクラスにこの機能と追加の機能を実装する方法について説明し <xref:System.Windows.Forms.ToolStripMenuItem> ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="6e6ad-109">クラスは、 `ToolStripRadioButtonMenuItem` やなどのメンバーをオーバーライドして、 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> オプションボタンの選択動作と外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="6e6ad-110">また、このクラスは、 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 親項目が選択されていない場合にサブメニューのオプションが無効になるように、プロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="6e6ad-111">オプションボタンの選択動作を実装するには</span><span class="sxs-lookup"><span data-stu-id="6e6ad-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="6e6ad-112">項目の選択を有効にするには、プロパティをに初期化し <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="6e6ad-113"><xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>新しい項目を選択したときに、前に選択した項目の選択を解除するには、メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="6e6ad-114">メソッドをオーバーライドして、 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 既に選択されている項目をクリックしても選択内容がクリアされないようにします。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="6e6ad-115">オプションボタンの項目の外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="6e6ad-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="6e6ad-116"><xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>クラスを使用して、既定のチェックマークをオプションボタンに置き換えるには、メソッドをオーバーライドし <xref:System.Windows.Forms.RadioButtonRenderer> ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="6e6ad-117">、、 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> 、およびの各メソッドをオーバーライドして <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> マウスの状態を追跡し、 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> メソッドが適切なオプションボタンの状態を描画するようにします。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="6e6ad-118">親項目が選択されていないときにサブメニューのオプションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="6e6ad-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="6e6ad-119"><xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>の値と値の両方を持つ親項目がある場合に、項目が無効になるように、プロパティをオーバーライドし <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="6e6ad-120"><xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>親アイテムのイベントをサブスクライブするには、メソッドをオーバーライドし <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="6e6ad-121">親項目のイベントのハンドラーで <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 、項目を無効にして、新しい有効な状態で表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="6e6ad-122">例</span><span class="sxs-lookup"><span data-stu-id="6e6ad-122">Example</span></span>

<span data-ttu-id="6e6ad-123">次のコード例では、完全な `ToolStripRadioButtonMenuItem` クラスと、 <xref:System.Windows.Forms.Form> オプションボタンの動作を示すクラスとクラスを提供して `Program` います。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="6e6ad-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6e6ad-124">Compiling the Code</span></span>

<span data-ttu-id="6e6ad-125">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-125">This example requires:</span></span>

- <span data-ttu-id="6e6ad-126">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="6e6ad-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e6ad-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e6ad-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="6e6ad-128">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="6e6ad-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="6e6ad-129">方法: カスタムの ToolStripRenderer を実装する</span><span class="sxs-lookup"><span data-stu-id="6e6ad-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
