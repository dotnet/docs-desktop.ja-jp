---
title: コントロールを固定する
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: e7bc514f7347f257a6e2df67571c09df78f3c547
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957164"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>方法: Windows フォームのコントロールを固定する

実行時にユーザーがサイズ変更できるフォームをデザインする場合は、フォーム上のコントロールのサイズと位置が適切に変更される必要があります。 フォームを使用してコントロールのサイズを動的に変更するには、 <xref:System.Windows.Forms.Control.Anchor%2A> Windows フォームコントロールのプロパティを使用します。 プロパティは、 <xref:System.Windows.Forms.Control.Anchor%2A> コントロールのアンカー位置を定義します。 コントロールがフォームに固定され、フォームのサイズが変更されると、コントロールは、コントロールとアンカー位置との距離を維持します。 たとえば、フォーム <xref:System.Windows.Forms.TextBox> のサイズが変更されたときにフォームの左端、右端、および下端に固定されているコントロールがある場合は、 <xref:System.Windows.Forms.TextBox> フォームの右端と左端から同じ距離が維持されるように、コントロールが水平方向にサイズ変更されます。 また、コントロールは、その位置が常にフォームの下端から同じ距離になるように垂直方向に配置されます。 コントロールが固定されておらず、フォームのサイズが変更されている場合は、フォームの端を基準としたコントロールの位置が変更されます。

プロパティは、 <xref:System.Windows.Forms.Control.Anchor%2A> プロパティと対話し <xref:System.Windows.Forms.Control.AutoSize%2A> ます。 詳細については、「[AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。

## <a name="anchor-a-control-on-a-form"></a>フォームにコントロールを固定する

1. Visual Studio で、アンカーするコントロールを選択します。

    > [!NOTE]
    > 複数のコントロールを同時に固定するには、CTRL キーを押しながら各コントロールをクリックして選択し、この手順の残りの部分を実行します。

2. [ **プロパティ** ] ウィンドウで、プロパティの右側にある矢印をクリックし <xref:System.Windows.Forms.Control.Anchor%2A> ます。

     クロスを示すエディターが表示されます。

3. アンカーを設定するには、交差部分の上、左、右、または下のセクションをクリックします。

     既定では、コントロールは上と左に固定されています。

4. アンカーされているコントロールの辺をクリアするには、クロスの arm をクリックします。

5. プロパティエディターを閉じるには <xref:System.Windows.Forms.Control.Anchor%2A> 、 <xref:System.Windows.Forms.Control.Anchor%2A> プロパティ名をもう一度クリックします。

実行時にフォームを表示すると、フォームの端と同じ距離に配置されたままになるようにコントロールのサイズが変更されます。 固定されたエッジからの距離は、コントロールが Windows フォームデザイナーに配置されているときに定義されている距離と常に同じままです。

> [!NOTE]
> コントロールなどの特定のコントロールの <xref:System.Windows.Forms.ComboBox> 高さには制限があります。 コントロールをフォームまたはコンテナーの下部に固定すると、コントロールの高さの制限を超えることはありません。

継承されたコントロールを固定できるようにする必要があり `Protected` ます。 コントロールのアクセスレベルを変更するには、 `Modifiers` [ **プロパティ** ] ウィンドウでプロパティを設定します。

## <a name="see-also"></a>関連項目

- [Windows フォームコントロール](index.md)
- [AutoSize プロパティの概要](autosize-property-overview.md)
- [方法 : Windows フォーム上のコントロールをドッキングする](how-to-dock-controls-on-windows-forms.md)
- [チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [チュートリアル: Padding、Margin、AutoSize プロパティを使用した Windows フォーム コントロールのレイアウト](windows-forms-controls-padding-autosize.md)
