---
title: '方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982252"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する

との各プロパティを使用して、コントロールの配置と伸縮を行うことができ <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.Control.Anchor%2A> <xref:System.Windows.Forms.Control.Dock%2A> ます。

## <a name="align-and-stretch-a-control"></a>コントロールを配置して伸縮する

1. Visual Studio で、 <xref:System.Windows.Forms.TableLayoutPanel> **ツールボックス** からコントロールをフォームにドラッグします。

2. [ツールボックス] からコントロールをドラッグして、 <xref:System.Windows.Forms.Button> コントロールの左上のセルに移動し <xref:System.Windows.Forms.TableLayoutPanel> ます。 <xref:System.Windows.Forms.Button>コントロールがセルの中央に配置されます。

3. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し `Left,Right` ます。 コントロールは、 <xref:System.Windows.Forms.Button> セルの幅に合わせて拡大されます。

4. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し `Top,Bottom` ます。 コントロールは、 <xref:System.Windows.Forms.Button> セルの高さに合わせて拡大されます。

5. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Dock%2A> をに設定し <xref:System.Windows.Forms.DockStyle.Fill> ます。 <xref:System.Windows.Forms.Button>コントロールがセルに合わせて拡大されます。

6. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Dock%2A> をに設定し <xref:System.Windows.Forms.DockStyle.None> ます。 <xref:System.Windows.Forms.Button>コントロールは元のサイズに戻り、セルの左上隅に移動します。 **Windows フォームデザイナー** によってプロパティがに設定されてい <xref:System.Windows.Forms.Control.Anchor%2A> `Top, Left` ます。

7. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し `Bottom,Right` ます。 <xref:System.Windows.Forms.Button>コントロールがセルの右下隅に移動します。

8. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し <xref:System.Windows.Forms.AnchorStyles.None> ます。 <xref:System.Windows.Forms.Button>コントロールがセルの中央に移動します。

## <a name="see-also"></a>関連項目

- [TableLayoutPanel コントロール](tablelayoutpanel-control-windows-forms.md)
