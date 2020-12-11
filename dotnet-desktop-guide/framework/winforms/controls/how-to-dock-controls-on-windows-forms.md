---
title: コントロールをドッキングする
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982524"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>方法: Windows フォームにコントロールをドッキングする

コントロールをフォームの端にドッキングしたり、コントロールのコンテナー (フォームまたはコンテナーコントロールのいずれか) に入力したりすることができます。 たとえば、Windows エクスプローラーでは、ウィンドウの左側にコントロールがドッキングさ <xref:System.Windows.Forms.TreeView> れ、 <xref:System.Windows.Forms.ListView> コントロールはウィンドウの右側に表示されます。 <xref:System.Windows.Forms.Control.Dock%2A>ドッキングモードを定義するには、表示されているすべての Windows フォームコントロールに対してプロパティを使用します。

> [!NOTE]
> コントロールは、逆 z オーダーでドッキングされます。

プロパティは、 <xref:System.Windows.Forms.Control.Dock%2A> プロパティと対話し <xref:System.Windows.Forms.Control.AutoSize%2A> ます。 詳細については、「[AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。

## <a name="to-dock-a-control"></a>コントロールをドッキングするには

1. Visual Studio で、ドッキングするコントロールを選択します。

2. [ **プロパティ** ] ウィンドウで、プロパティの右側にある矢印をクリックし <xref:System.Windows.Forms.Control.Dock%2A> ます。

   フォームの端と中央を表す一連のボックスを示すエディターが表示されます。

3. コントロールをドッキングするフォームの端を表すボタンをクリックします。 コントロールのフォームまたはコンテナーコントロールの内容を塗りつぶすには、中央のボックスをクリックします。 [ **(なし)** ] をクリックして、ドッキングを無効にします。

   ドッキングされた端の境界に合わせてコントロールのサイズが自動的に変更されます。

   > [!NOTE]
   > 継承されたコントロールは、ドッキングできる必要があり `Protected` ます。 コントロールのアクセスレベルを変更するには、[**プロパティ**] ウィンドウでその [**修飾子**] プロパティを設定します。

## <a name="see-also"></a>関連項目

- [Windows フォームコントロール](index.md)
- [各 Windows フォーム コントロールのラベル設定とショートカットの作成](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
- [Windows フォーム コントロールの機能別一覧](windows-forms-controls-by-function.md)
- [方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [方法 : TableLayoutPanel コントロールで子コントロールを固定およびドッキングする](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [AutoSize プロパティの概要](autosize-property-overview.md)
- [方法 : Windows フォームにコントロールを固定する](how-to-anchor-controls-on-windows-forms.md)
