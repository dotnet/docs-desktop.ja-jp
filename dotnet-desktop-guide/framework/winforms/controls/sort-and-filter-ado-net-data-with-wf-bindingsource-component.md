---
title: BindingSource コンポーネントを使用した ADO.NET データの並べ替えとフィルター処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 404e67f1eeed240a171cb1cfef9094a746c3cecb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974376"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>方法: Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する

プロパティとプロパティを使用して、コントロールの並べ替えとフィルター処理の機能を公開でき <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Sort%2A> <xref:System.Windows.Forms.BindingSource.Filter%2A> ます。 基になるデータソースがである場合は、単純な並べ替えを適用でき <xref:System.ComponentModel.IBindingList> ます。また、データソースがの場合は、フィルター処理や高度な並べ替えを適用でき <xref:System.ComponentModel.IBindingListView> ます。 プロパティには、 <xref:System.Windows.Forms.BindingSource.Sort%2A> 標準の ADO.NET 構文が必要です。これには、データソース内のデータ列の名前を表す文字列、 `ASC` または `DESC` リストを昇順と降順のどちらで並べ替えるかを示す、またはが必要です。 各列をコンマ区切り記号で区切ることによって、高度な並べ替えまたは複数列の並べ替えを設定できます。 プロパティは、 <xref:System.Windows.Forms.BindingSource.Filter%2A> 文字列式を受け取ります。  
  
> [!NOTE]
> 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。  
  
### <a name="to-filter-data-with-the-bindingsource"></a>BindingSource を使用してデータをフィルター処理するには  
  
- プロパティを <xref:System.Windows.Forms.BindingSource.Filter%2A> 目的の式に設定します。  
  
     次のコード例では、式は列名の後に列に必要な値を指定しています。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>BindingSource を使用してデータを並べ替えるには  
  
1. プロパティに、 <xref:System.Windows.Forms.BindingSource.Sort%2A> またはを使用して昇順または降順を示す列名を設定し `ASC` `DESC` ます。  
  
2. 複数の列をコンマで区切ります。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>例  

 次のコード例では、Northwind サンプルデータベースの Customers テーブルからコントロールにデータを読み込み、 <xref:System.Windows.Forms.DataGridView> 表示されるデータをフィルター処理して並べ替えます。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  

 この例を実行するには、という名前のとという名前のを含むフォームにコードを貼り付け <xref:System.Windows.Forms.BindingSource> `BindingSource1` <xref:System.Windows.Forms.DataGridView> `dataGridView1` ます。 フォームのイベントを処理し、 <xref:System.Windows.Forms.Form.Load> `InitializeSortedFilteredBindingSource` load イベントハンドラーメソッドでを呼び出します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [方法 : サンプル データベースをインストールする](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource コンポーネント](bindingsource-component.md)
