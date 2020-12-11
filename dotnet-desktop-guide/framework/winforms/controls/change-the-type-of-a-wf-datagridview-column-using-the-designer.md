---
title: デザイナーを使用して DataGridView 列の型を変更する
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 470f350a4791a3db39d08ab7992d86eb7b2e270a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981560"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>方法: デザイナーを使用して Windows フォーム DataGridView 列の種類を変更する
Windows フォームコントロールに既に追加されている列の型を変更することが必要になる場合があり <xref:System.Windows.Forms.DataGridView> ます。 たとえば、データソースにコントロールをバインドするときに自動的に生成されるいくつかの列の型を変更することができます。 これは、表示するテーブルに、関連テーブル内の行に対する外部キーを含む列がある場合に便利です。 この場合は、これらの外部キーを表示するテキストボックスの列を、関連するテーブルの意味のある値を表示するコンボボックスの列に置き換えることができます。

 次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>デザイナーを使用して列の型を変更するには

1. コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) 列の <xref:System.Windows.Forms.DataGridView> **編集**] を選択します。

2. [ **選択された列** ] ボックスの一覧から列を選択します。

3. [ **列のプロパティ** ] グリッドで、 `ColumnType` プロパティを新しい列の種類に設定します。

    > [!NOTE]
    > `ColumnType`プロパティは、列の型を表すクラスを示すデザイン時専用のプロパティです。 これは、列クラスで定義された実際のプロパティではありません。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [方法: Windows フォームアプリケーションプロジェクトを作成する](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [方法: Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)
