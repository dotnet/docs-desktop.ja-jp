---
title: '方法: ToolStrip オーバーフローを管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974802"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>方法 : Windows フォームの ToolStrip オーバーフローを管理する

割り当てられた領域にコントロールのすべての項目が <xref:System.Windows.Forms.ToolStrip> 収まらない場合は、のオーバーフロー機能を有効に <xref:System.Windows.Forms.ToolStrip> し、特定ののオーバーフロー動作を決定することができ <xref:System.Windows.Forms.ToolStripItem> ます。

指定された <xref:System.Windows.Forms.ToolStripItem> フォームの現在のサイズよりも多くの領域を必要とするを追加すると、が <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripOverflowButton> 自動的にに表示され <xref:System.Windows.Forms.ToolStrip> ます。 <xref:System.Windows.Forms.ToolStripOverflowButton>が表示され、オーバーフローに対応する項目がドロップダウンオーバーフローメニューに移動します。 これにより、 <xref:System.Windows.Forms.ToolStrip> さまざまなフォームサイズに合わせて項目を適切に調整する方法をカスタマイズし、優先順位を付けることができます。 また、 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> プロパティとプロパティ、およびイベントを使用して、項目がオーバーフローになったときの外観を変更することもでき <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> ます。 デザイン時または実行時にフォームを拡大すると、 <xref:System.Windows.Forms.ToolStripItem> メインにより多くのが表示され、 <xref:System.Windows.Forms.ToolStrip> フォームのサイズを小さくするまではが表示されなくなる場合が <xref:System.Windows.Forms.ToolStripOverflowButton> あります。

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>ToolStrip コントロールでオーバーフローを有効にするには

- のプロパティがに設定されていないことを確認し <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> `false` <xref:System.Windows.Forms.ToolStrip> ます。 既定値は、`True` です。

     <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>が `True` (既定値) の場合、 <xref:System.Windows.Forms.ToolStripItem> のコンテンツが <xref:System.Windows.Forms.ToolStripItem> 水平方向または垂直方向の高さを超えたときに、ドロップダウンオーバーフローメニューにが送信され <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> ます。

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>特定の ToolStripItem のオーバーフロー動作を指定するには

- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>のプロパティ <xref:System.Windows.Forms.ToolStripItem> を目的の値に設定します。 その可能性は `Always` 、、、 `Never` および `AsNeeded` です。 既定値は、`AsNeeded` です。

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
- [ToolStrip コントロールのアーキテクチャ](toolstrip-control-architecture.md)
- [ToolStrip テクノロジの概要](toolstrip-technology-summary.md)
