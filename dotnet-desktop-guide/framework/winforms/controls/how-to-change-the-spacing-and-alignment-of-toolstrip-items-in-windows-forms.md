---
title: '方法: ToolStrip 項目の間隔と配置を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982215"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>方法: Windows フォーム内の ToolStrip 項目の間隔と配置を変更する
コントロールは、 <xref:System.Windows.Forms.ToolStrip> サイズ変更、相互に相対的なコントロールの間隔、 <xref:System.Windows.Forms.ToolStripItem> 上のコントロールの配置、およびを基準としたコントロールの間隔などのレイアウト機能を完全にサポートし <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> ます。  
  
 プロパティの既定値はであるため <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> `true` 、プロパティをに設定しない限り、コントロールのサイズは自動的に変更され <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> `false` ます。  
  
### <a name="to-manually-size-a-toolstripitem"></a>ToolStripItem のサイズを手動で変更するには  
  
1. <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>関連付けられたコントロールのプロパティをに設定し `false` ます。  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. 関連するに対して、プロパティを必要に応じて設定し <xref:System.Windows.Forms.ToolStripItem.Size%2A> <xref:System.Windows.Forms.ToolStripItem> ます。  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>ToolStripItem の間隔を設定するには  
  
1. 目的の値をピクセル単位で、 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 関連付けられているコントロールのプロパティに挿入します。  
  
     プロパティの値は、 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 項目と隣接する項目の間の間隔を、左、上、右、下の順に指定します。  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>ToolStripItem を ToolStrip の右側に配置するには  
  
1. <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>関連付けられたコントロールのプロパティをに設定し <xref:System.Windows.Forms.ToolStripItemAlignment.Right> ます。 既定で <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> は、はに設定されます。これにより、コントロールがの <xref:System.Windows.Forms.ToolStripItemAlignment.Left> 左側に配置され <xref:System.Windows.Forms.ToolStrip> ます。  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Toolstrip に ToolStrip 項目を配置するには  
  
- プロパティを、 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 目的のの値に設定し <xref:System.Windows.Forms.ToolStripLayoutStyle> ます。  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
- [ToolStrip コントロールのアーキテクチャ](toolstrip-control-architecture.md)
- [ToolStrip テクノロジの概要](toolstrip-technology-summary.md)
