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
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>方法 : MenuStrip にオプション ボタンを表示する (Windows フォーム)

オプションボタンは、オプションボタンとも呼ばれ、ユーザーが一度に1つだけ選択できる点を除いて、チェックボックスに似ています。 既定では、 <xref:System.Windows.Forms.ToolStripMenuItem> クラスにはオプションボタンの動作が用意されていませんが、クラスには、コントロールのメニュー項目に対してオプションボタンの動作を実装するようにカスタマイズできるチェックボックスの動作が用意されてい <xref:System.Windows.Forms.MenuStrip> ます。

<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>メニュー項目のプロパティがの場合 `true` 、ユーザーは項目をクリックしてチェックマークの表示を切り替えることができます。 プロパティは、 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 項目の現在の状態を示します。 基本的なオプションボタンの動作を実装するには、項目が選択されているときに、前に選択した項目のプロパティをに設定する必要があり <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false` ます。

次の手順では、クラスを継承するクラスにこの機能と追加の機能を実装する方法について説明し <xref:System.Windows.Forms.ToolStripMenuItem> ます。 クラスは、 `ToolStripRadioButtonMenuItem` やなどのメンバーをオーバーライドして、 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> オプションボタンの選択動作と外観を提供します。 また、このクラスは、 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 親項目が選択されていない場合にサブメニューのオプションが無効になるように、プロパティをオーバーライドします。

## <a name="to-implement-option-button-selection-behavior"></a>オプションボタンの選択動作を実装するには

1. 項目の選択を有効にするには、プロパティをに初期化し <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` ます。

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>新しい項目を選択したときに、前に選択した項目の選択を解除するには、メソッドをオーバーライドします。

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. メソッドをオーバーライドして、 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 既に選択されている項目をクリックしても選択内容がクリアされないようにします。

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>オプションボタンの項目の外観を変更するには

1. <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>クラスを使用して、既定のチェックマークをオプションボタンに置き換えるには、メソッドをオーバーライドし <xref:System.Windows.Forms.RadioButtonRenderer> ます。

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. 、、 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> 、およびの各メソッドをオーバーライドして <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> マウスの状態を追跡し、 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> メソッドが適切なオプションボタンの状態を描画するようにします。

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>親項目が選択されていないときにサブメニューのオプションを無効にするには

1. <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>の値と値の両方を持つ親項目がある場合に、項目が無効になるように、プロパティをオーバーライドし <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false` ます。

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>親アイテムのイベントをサブスクライブするには、メソッドをオーバーライドし <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> ます。

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. 親項目のイベントのハンドラーで <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 、項目を無効にして、新しい有効な状態で表示を更新します。

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>例

次のコード例では、完全な `ToolStripRadioButtonMenuItem` クラスと、 <xref:System.Windows.Forms.Form> オプションボタンの動作を示すクラスとクラスを提供して `Program` います。

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>コードのコンパイル

この例で必要な要素は次のとおりです。

- System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [MenuStrip コントロール](menustrip-control-windows-forms.md)
- [方法: カスタムの ToolStripRenderer を実装する](how-to-implement-a-custom-toolstriprenderer.md)
