---
title: '方法 : デザイン時にフォームの端に合わせてコントロールを配置する'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982255"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>方法 : デザイン時にフォームの端に合わせてコントロールを配置する

プロパティの値を設定することによって、コントロールをフォームの端に合わせることができ <xref:System.Windows.Forms.Control.Dock%2A> ます。 このプロパティは、フォーム内のコントロールの場所を指定します。 <xref:System.Windows.Forms.Control.Dock%2A> プロパティには次の値のいずれかを設定できます。

|設定|コントロールへの影響|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|フォームの下部にドッキングします。|
|<xref:System.Windows.Forms.DockStyle.Fill>|フォームの残りの全スペースを埋めます。|
|<xref:System.Windows.Forms.DockStyle.Left>|フォームの左側にドッキングします。|
|<xref:System.Windows.Forms.DockStyle.None>|はどこにもドッキングせず、で指定した場所に表示され <xref:System.Windows.Forms.Control.Location%2A> ます。|
|<xref:System.Windows.Forms.DockStyle.Right>|フォームの右側にドッキングします。|
|<xref:System.Windows.Forms.DockStyle.Top>|フォームの上部にドッキングします。|

これらの値は、コードで設定することもできます。 詳細については、「 [方法: フォームの端にコントロールを配置する](how-to-align-a-control-to-the-edges-of-forms.md)」を参照してください。

## <a name="set-the-dock-property-for-your-control-at-design-time"></a>デザイン時にコントロールの Dock プロパティを設定する

1. Visual Studio の Windows フォームデザイナーで、コントロールを選択します。

2. [ **プロパティ** ] ウィンドウで、プロパティの横にあるドロップダウンボックスをクリックし <xref:System.Windows.Forms.Control.Dock%2A> ます。

     6つの設定を表すグラフィカルインターフェイス <xref:System.Windows.Forms.Control.Dock%2A> が表示されます。

3. 適切な設定を選択します。

4. これで、設定によって指定された方法でコントロールがドッキングされるようになります。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [方法: フォームの端に合わせてコントロールを配置する](how-to-align-a-control-to-the-edges-of-forms.md)
- [チュートリアル : スナップ線を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [方法 : Windows フォームにコントロールを固定する](how-to-anchor-controls-on-windows-forms.md)
- [方法 : TableLayoutPanel コントロールで子コントロールを固定およびドッキングする](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [デザイン時の Windows フォーム コントロールの開発](developing-windows-forms-controls-at-design-time.md)
