---
title: デザイナーを使用して DataGridView コントロールにデータをバインドする
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 6a8ffdbf950eb0fcda7b4752e6e9dd73a6df3f6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975121"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>方法: デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインドする

デザイナーを使用すると <xref:System.Windows.Forms.DataGridView> 、データベース、ビジネスオブジェクト、Web サービスなど、さまざまな種類のデータソースにコントロールを接続できます。 デザイナーを使用してコントロールをデータソースにバインドすると、コントロールはデータソースを表すコンポーネントに自動的にバインドされ <xref:System.Windows.Forms.BindingSource> ます。 さらに、データ ソースによって提供されるスキーマ情報に対応するように、このコントロールの列が自動的に生成されます。

 列が生成された後に、ニーズに合わせて列を変更できます。 たとえば、表示に関係のない列を削除または非表示にしたり、列の順序を変更したり、列の型を変更したりすることができます。 列の変更の詳細については、「関連項目」セクションの各トピックを参照してください。

 また、関連テーブルに複数のコントロールをバインドして、 <xref:System.Windows.Forms.DataGridView> マスター/詳細リレーションシップを作成することもできます。 この構成では、1 つのコントロールに親テーブルが表示され、別のコントロールには親テーブルの現在の行に関連する子テーブルの行のみが表示されます。 詳細については、「[方法: 関連するデータを Windows フォーム アプリケーションに表示する](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))」を参照してください。

 次の手順では 、 <xref:System.Windows.Forms.DataGridView> マスター/詳細リレーションシップのコントロールまたは2つのコントロールを含むフォームを含む Windows アプリケーションプロジェクトが必要です。 このようなプロジェクトを開始する方法の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

## <a name="to-bind-the-control-to-a-data-source"></a>コントロールをデータ ソースにバインドするには

1. ![ ](./media/designer-actions-glyph.gif) コントロールの右上隅にある [デザイナーアクション] グリフ (小さい黒い矢印) をクリックし <xref:System.Windows.Forms.DataGridView> ます。

2. **[データ ソースの選択]** オプションのドロップダウン矢印をクリックします。

3. プロジェクトにまだデータ ソースがない場合は、**[プロジェクト データ ソースの追加]** をクリックし、ウィザードに示される手順に従います。

     詳細については、「[データ ソース構成ウィザード](/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120))」を参照してください。 **[データ ソースの選択]** ドロップダウン ウィンドウに新しいデータ ソースが表示されます。 新しいデータ ソースに含まれるのが単一データベース テーブルなど、1 つのメンバーのみの場合、コントロールはそのメンバーに自動的にバインドされます。 使用する場合は、次の手順に進みます。

4. 展開されていない場合は **[他のデータ ソース]** ノードと **[プロジェクト データ ソース]** ノードを展開し、コントロールをバインドするデータ ソースを選択します。

5. 複数のテーブルを含むを作成した場合など、データソースに複数のメンバーが含まれている場合は、 <xref:System.Data.DataSet?displayProperty=nameWithType> データソースを展開し、バインド先の特定のメンバーを選択します。

6. マスター/詳細リレーションシップを作成するには、[ **データソースの選択** ] ドロップダウンウィンドウで、親テーブル用に作成したを展開し、表示されている <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> 一覧から関連する子テーブルを選択します。

    > [!NOTE]
    > プロジェクトにデータ ソースが既にある場合は、**[データソース]** ウィンドウを使用してデータ フォームを作成することもできます。 詳細については、「[[データ ソース] ウィンドウ](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [方法 : データベース内のデータに接続する](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の順序を変更する](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [方法: デザイナーを使用して Windows フォーム DataGridView 列の種類を変更する](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する](freeze-columns-in-the-datagrid-using-the-designer.md)
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする](hide-columns-in-the-datagrid-using-the-designer.md)
- [方法: デザイナーを使用して Windows フォームの DataGridView コントロールで列を読み取り専用にする](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [方法: Windows フォームアプリケーションプロジェクトを作成する](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [方法: Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)
- [データ ソース ウィンドウ](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [方法: 関連するデータを Windows フォーム アプリケーションに表示する](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
