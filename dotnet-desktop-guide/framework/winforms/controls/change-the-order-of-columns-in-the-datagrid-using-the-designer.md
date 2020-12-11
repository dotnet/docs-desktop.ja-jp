---
title: デザイナーを使用して DataGridView コントロールの列の順序を変更する
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975109"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の順序を変更する

Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールをデータソースにバインドすると、自動的に生成された列の表示順序はデータソースによって決まります。 この順序が希望どおりでない場合は、デザイナーを使用して列の順序を変更できます。 コントロールに非バインド列を追加して、表示順序を変更することもできます。 プログラムによって列の順序を変更する方法の詳細については、「 [方法: Windows フォーム DataGridView コントロールの列の順序を変更](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)する」を参照してください。

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

## <a name="to-change-the-column-order-using-the-designer"></a>デザイナーを使用して列の順序を変更するには

1. コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) 列の <xref:System.Windows.Forms.DataGridView> **編集**] を選択します。

2. [ **選択された列** ] ボックスの一覧から列を選択します。

3. [ **選択さ** れた列] の一覧の右側にある上矢印または下矢印をクリックすると、選択した列が目的の位置に表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [方法: Windows フォームアプリケーションプロジェクトを作成する](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [方法: Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)
