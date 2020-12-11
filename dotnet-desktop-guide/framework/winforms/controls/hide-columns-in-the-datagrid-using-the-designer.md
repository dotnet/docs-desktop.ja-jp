---
title: デザイナーを使用して DataGridView コントロールの列を非表示にする
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: c5344e10a69d86b1733f5462f9c2df0f0e71b8d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981480"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする
Windows フォームの <xref:System.Windows.Forms.DataGridView> コントロールで使用できる列の一部のみを表示したいときがあります。 たとえば、管理資格情報を持つユーザーに employee salary 列を表示し、他のユーザーには表示しないようにすることができます。 または、いくつかの列を含むデータソースにコントロールをバインドし、その一部のみを表示することもできます。 この場合、通常は、表示されていない列を非表示にするのではなく、削除します。 詳細については、「 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールで列を追加および削除](add-and-remove-columns-in-the-datagrid-using-the-designer.md)する」を参照してください。

 次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

## <a name="to-hide-a-column-using-the-designer"></a>デザイナーを使用して列を非表示にするには

1. コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) 列の <xref:System.Windows.Forms.DataGridView> **編集**] を選択します。

2. [ **選択された列** ] ボックスの一覧から列を選択します。

3. 列の **プロパティ** グリッドで、 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> プロパティをに設定し `false` ます。

    > [!NOTE]
    > [**列の追加**] ダイアログボックスの [**表示**] チェックボックスをオフにすることで、列を追加するときに非表示にすることもできます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [方法: Windows フォームアプリケーションプロジェクトを作成する](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [方法: Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)
