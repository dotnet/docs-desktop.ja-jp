---
title: デザイナーを使用して DataGrid コントロールにテーブルと列を追加する
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 7d00deb453793f7fc1f1c5d59913cb704ad546d9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981104"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>方法: デザイナーを使って Windows フォーム DataGrid コントロールにテーブルと列を追加する

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。

<xref:System.Windows.Forms.DataGrid>オブジェクトを作成 <xref:System.Windows.Forms.DataGridTableStyle> し、 <xref:System.Windows.Forms.GridTableStylesCollection> <xref:System.Windows.Forms.DataGrid> コントロールのプロパティを使用してアクセスするオブジェクトに追加することにより、テーブルおよび列の Windows フォームコントロールにデータを表示できます <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 。 各テーブルスタイルには、のプロパティで指定されているデータテーブルの内容が表示され <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> <xref:System.Windows.Forms.DataGridTableStyle> ます。 既定では、列スタイルが指定されていないテーブルスタイルでは、そのデータテーブル内のすべての列が表示されます。 にオブジェクトを追加することで、テーブル内のどの列を表示するかを制限できます。このオブジェクトには、 <xref:System.Windows.Forms.DataGridColumnStyle> <xref:System.Windows.Forms.GridColumnStylesCollection> 各のプロパティを通じてアクセスし <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> <xref:System.Windows.Forms.DataGridTableStyle> ます。

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGrid> 。 このようなプロジェクトを設定する方法については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。 既定では、Visual Studio 2005 で <xref:System.Windows.Forms.DataGrid> は、コントロールは **ツールボックス** に含まれていません。 追加の詳細については、「 [方法: 項目をツールボックスに追加](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))する」を参照してください。

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>デザイナーで DataGrid コントロールにテーブルを追加するには

1. テーブルにデータを表示するには、最初にコントロールをデータセットにバインドする必要があり <xref:System.Windows.Forms.DataGrid> ます。 詳細については、「 [方法: デザイナーを使用してデータソースに Windows フォーム DataGrid コントロールをバインド](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)する」を参照してください。

2. [プロパティウィンドウでコントロールのプロパティを選択し、プロパティの横にある省略記号ボタン ([. <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGrid.TableStyles%2A> ..] プロパティウィンドウ) をクリックして、 ![ ](./media/visual-studio-ellipsis-button.png) **DataGridTableStyle Collection エディター** を表示します。

3. コレクションエディターで、[ **追加** ] をクリックしてテーブルのスタイルを挿入します。

4. [ **OK** ] をクリックしてコレクションエディターを閉じ、プロパティの横にある省略記号ボタンをクリックして再度開き <xref:System.Windows.Forms.DataGrid.TableStyles%2A> ます。

     コレクションエディターを再度開くと、コントロールにバインドされているすべてのデータテーブルが、テーブルスタイルのプロパティのドロップダウンリストに表示され <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> ます。

5. コレクションエディターの [ **メンバー** ] ボックスで、テーブルのスタイルをクリックします。

6. コレクションエディターの [ **プロパティ** ] ボックスで、表示する <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> テーブルの値を選択します。

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>デザイナーで DataGrid コントロールに列を追加するには

1. **DataGridTableStyle コレクションエディター** の [**メンバー** ] ボックスで、適切なテーブルのスタイルを選択します。 コレクションエディターの [ **プロパティ** ] ボックスで、コレクションを選択します。次に、プロパティの横にある省略記号ボタン ([.. プロパティウィンドウ.]) をクリックして、 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> ![ ](./media/visual-studio-ellipsis-button.png) **system.windows.forms.datagridcolumnstyle> collection エディター** を表示します。

2. コレクションエディターで、[ **追加** ] をクリックして列のスタイルを挿入するか、[ **追加** ] の横にある下矢印をクリックして列の種類を指定します。

     ドロップダウンボックスで、またはのいずれかの種類を選択でき <xref:System.Windows.Forms.DataGridTextBoxColumn> <xref:System.Windows.Forms.DataGridBoolColumn> ます。

3. [OK] をクリックして **System.windows.forms.datagridcolumnstyle> Collection エディター** を閉じ、プロパティの横にある省略記号ボタンをクリックして再度開き <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> ます。

     コレクションエディターを再度開くと、バインドされたデータテーブルのデータ列が、列スタイルのプロパティのドロップダウンリストに表示され <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> ます。

4. コレクションエディターの [ **メンバー** ] ボックスで、列のスタイルをクリックします。

5. コレクションエディターの [ **プロパティ** ] ボックスで、表示する <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 列の値を選択します。

## <a name="see-also"></a>関連項目

- [DataGrid コントロール](datagrid-control-windows-forms.md)
- [方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
