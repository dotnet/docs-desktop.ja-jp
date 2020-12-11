---
title: 2つの DataGridView コントロールを使用して Master-Detail フォームを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: d490af6517e7e45bb2dd48ab7d41c468a7eba2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974263"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>方法: Windows フォームの 2 つの DataGridView コントロールを使用してマスター/詳細形式のフォームを作成する

次のコード例では、2 つの <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドされた 2 つの <xref:System.Windows.Forms.DataGridView> コントロールを使用してマスター/詳細フォームを作成します。 データ ソースが、Northwind SQL Server のサンプル データベース、および `CustomerID` 列により 2 つに関連する <xref:System.Data.DataRelation> からの `Customers` テーブルと `Orders` テーブルを含む <xref:System.Data.DataSet> です。  
  
 1 つの <xref:System.Windows.Forms.BindingSource> はデータセットの親 `Customers` テーブルにバインドされます。 このデータは、マスタ <xref:System.Windows.Forms.DataGridView> コントロールに表示されます。 もう一方の <xref:System.Windows.Forms.BindingSource> は、最初のデータ コネクタにバインドされます。 2 つ目の <xref:System.Windows.Forms.BindingSource> の <xref:System.Windows.Forms.BindingSource.DataMember%2A> プロパティは、<xref:System.Data.DataRelation> の名前に設定されます。 これにより、関連付けられている詳細の <xref:System.Windows.Forms.DataGridView> コントロールが、マスター <xref:System.Windows.Forms.DataGridView> コントロールの現在の行に対応する子の `Orders` テーブルの行を表示します。  
  
 このコード例の詳細については、「 [チュートリアル: 2 つの Windows フォーム DataGridView コントロールを使用してマスター/詳細フォームを作成](creating-a-master-detail-form-using-two-datagridviews.md)する」を参照してください。  
  
## <a name="example"></a>例  

 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  

 この例で必要な要素は次のとおりです。  
  
 System、System.Data、System.Windows.Forms、および System.XML の各アセンブリへの参照。  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  

 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームの作成](creating-a-master-detail-form-using-two-datagridviews.md)
- [Windows フォーム DataGridView コントロールでのデータの表示](displaying-data-in-the-windows-forms-datagridview-control.md)
- [接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)
