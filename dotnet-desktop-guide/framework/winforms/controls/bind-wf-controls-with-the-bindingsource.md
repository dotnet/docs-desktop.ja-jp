---
title: デザイナーを使用してコントロールを BindingSource コンポーネントにバインドする
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: ec4e556e855a2c86dc280e1c386e9dabc2319c57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981087"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>方法: デザイナーを使用して Windows フォーム コントロールを BindingSource コンポーネントにバインドする

フォームにコントロールを追加し、アプリケーションのユーザーインターフェイスを決定したら、コントロールをデータソースにバインドできます。これにより、ユーザーがアプリケーションに関連するデータを変更したり保存したりできるようになります。

 Windows フォームでコントロールまたは一連のコントロールをバインドすることは、 <xref:System.Windows.Forms.BindingSource> フォーム上のコントロールとデータソースの間のブリッジとして、コントロールを使用すると最も簡単に実現できます。

 フォーム上の1つ以上のコントロールをデータにバインドできます。次の手順では、 <xref:System.Windows.Forms.TextBox> コントロールがデータソースにバインドされます。

 この手順を完了するには、データベースから派生したデータソースにバインドすることを前提としています。 他のデータストアからデータソースを作成する方法の詳細については、「 [新しいデータソースの追加](/visualstudio/data-tools/add-new-data-sources)」を参照してください。

## <a name="to-bind-a-control-at-design-time"></a>デザイン時にコントロールをバインドするには

1. コントロールを <xref:System.Windows.Forms.TextBox> フォームにドラッグします。

2. [ **プロパティ** ] ウィンドウで、次のようにします。

    1. [ **(連結)** ] ノードを展開します。

    2. プロパティの横にある矢印をクリックし <xref:System.Windows.Forms.TextBox.Text%2A> ます。

         **DataSource** UI 型エディターが開きます。

         データソースが既にプロジェクトまたはフォーム用に構成されている場合は、そのデータソースが表示されます。

3. **[プロジェクト データ ソースの追加]** をクリックしてデータに接続し、データ ソースを作成します。

4. **データ ソース構成ウィザード** の開始ページで **[次へ]** をクリックします。

5. [ **データソースの種類を選択** ] ページで、[ **データベース**] を選択します。

6. [ **データ接続の選択** ] ページで、使用可能な接続の一覧からデータ接続を選択します。 目的のデータ接続が使用できない場合は、[ **新しい接続** ] を選択して新しいデータ接続を作成します。

7. [ **はい、接続を保存** します] を選択して、アプリケーション構成ファイルに接続文字列を保存します。

8. アプリケーションで使用するデータベース オブジェクトを選択します。 この場合、を表示するテーブルのフィールドを選択し <xref:System.Windows.Forms.TextBox> ます。

9. 必要な場合は、既定のデータセット名を変更します。

10. **[完了]** をクリックします。

11. [ **プロパティ** ] ウィンドウで、プロパティの横にある矢印を <xref:System.Windows.Forms.TextBox.Text%2A> もう一度クリックします。 **DataSource** UI 型エディターで、バインド先のフィールドの名前を選択し <xref:System.Windows.Forms.TextBox> ます。

     データ **ソース** UI 型エディターが閉じられ、データセットと、 <xref:System.Windows.Forms.BindingSource> そのデータ接続に固有のテーブルアダプターがフォームに追加されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [新しいデータ ソースの追加](/visualstudio/data-tools/add-new-data-sources)
- [データ ソース ウィンドウ](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
