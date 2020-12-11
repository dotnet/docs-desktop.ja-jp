---
title: サポートされるデータ ソース
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: b4c1c722790688ee638aa4de417664f697df3249
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981932"
---
# <a name="data-sources-supported-by-windows-forms"></a>Windows フォームがサポートするデータ ソース

従来、データベースに格納されているデータを利用するために、アプリケーション内でデータバインディングが使用されていました。 Windows フォームデータバインディングを使用すると、特定の最小要件が満たされていれば、データベースのデータだけでなく、配列やコレクションなどの他の構造体のデータにもアクセスできます。  
  
## <a name="structures-to-bind-to"></a>バインド先の構造体  

 Windows フォームでは、単純なオブジェクト (単純なバインド) から ADO.NET data tables (complex binding) などの複雑なリストにまで、さまざまな構造体にバインドできます。 単純なバインドの場合、Windows フォームは、単純なオブジェクトのパブリックプロパティへのバインドをサポートします。 Windows フォームリストベースのバインディングでは、通常、オブジェクトがインターフェイスまたはインターフェイスをサポートしている必要があり <xref:System.Collections.IList> <xref:System.ComponentModel.IListSource> ます。 また、コンポーネントを通じてバインドする場合は、 <xref:System.Windows.Forms.BindingSource> インターフェイスをサポートするオブジェクトにバインドでき <xref:System.Collections.IEnumerable> ます。 データバインディングに関連するインターフェイスの詳細については、「 [データバインディングに関連するインターフェイス](interfaces-related-to-data-binding.md)」を参照してください。  
  
 次の一覧は Windows フォームでバインドできる構造を示しています。  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource>は、最も一般的な Windows フォームデータソースであり、データソースと Windows フォームコントロールの間のプロキシ機能を果たします。 一般的な <xref:System.Windows.Forms.BindingSource> 使用パターンでは、コントロールをにバインド <xref:System.Windows.Forms.BindingSource> し、を <xref:System.Windows.Forms.BindingSource> データソース (たとえば、ADO.NET データテーブルまたはビジネスオブジェクト) にバインドします。 には、 <xref:System.Windows.Forms.BindingSource> データバインディングサポートのレベルを有効にし、改善するサービスが用意されています。 たとえば、やなどの Windows フォームリストベースのコントロールでは、 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.ComboBox> データソースへのバインドを直接サポートしていませんが、 <xref:System.Collections.IEnumerable> を使用してバインドすることで、このシナリオを有効にすることができ <xref:System.Windows.Forms.BindingSource> ます。 この場合、は <xref:System.Windows.Forms.BindingSource> データソースをに変換し <xref:System.Collections.IList> ます。  
  
 単純なオブジェクト  
 Windows フォームは、型を使用して、オブジェクトのインスタンスのパブリックプロパティに対するデータバインディングコントロールプロパティをサポートし <xref:System.Windows.Forms.Binding> ます。 Windows フォームでは、を使用する場合のオブジェクトインスタンスへのなど、バインドリストベースのコントロールもサポート <xref:System.Windows.Forms.ListControl> <xref:System.Windows.Forms.BindingSource> します。  
  
 配列またはコレクション  
 データソースとして機能するには、リストがインターフェイスを実装する必要があります <xref:System.Collections.IList> 。1つの例として、クラスのインスタンスである配列があり <xref:System.Array> ます。 配列の詳細については、「 [方法: オブジェクトの配列を作成する (Visual Basic)](/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100))」を参照してください。  
  
 一般に、 <xref:System.ComponentModel.BindingList%601> データバインディング用のオブジェクトのリストを作成する場合は、を使用する必要があります。 <xref:System.ComponentModel.BindingList%601> は、インターフェイスのジェネリックバージョンです <xref:System.ComponentModel.IBindingList> 。 インターフェイスは、 <xref:System.ComponentModel.IBindingList> <xref:System.Collections.IList> 双方向のデータバインディングに必要なプロパティ、メソッド、およびイベントを追加することによって、インターフェイスを拡張します。  
  
 <xref:System.Collections.IEnumerable>  
 Windows フォームコントロールは、 <xref:System.Collections.IEnumerable> コンポーネントを介してバインドされている場合にのみ、インターフェイスをサポートするデータソースにバインドでき <xref:System.Windows.Forms.BindingSource> ます。  
  
 ADO.NET data オブジェクト  
 ADO.NET には、へのバインドに適したさまざまなデータ構造体が用意されています。 それぞれの方法は、洗練され、複雑さによって異なります。  
  
- <xref:System.Data.DataColumn>. は、 <xref:System.Data.DataColumn> <xref:System.Data.DataTable> テーブルを構成する複数の列で構成されるの重要な構成要素です。 各 <xref:System.Data.DataColumn> には、 <xref:System.Data.DataColumn.DataType%2A> 列に保持されるデータの種類を決定するプロパティがあります (たとえば、自動車を説明するテーブルの自動車の作成)。 コントロール ( <xref:System.Windows.Forms.TextBox> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティなど) をデータテーブル内の列に単純にバインドすることができます。  
  
- <xref:System.Data.DataTable>. は、 <xref:System.Data.DataTable> ADO.NET に行と列を含むテーブルを表現したものです。 データテーブルには、次の2つのコレクションが含まれています。は、指定されたテーブル <xref:System.Data.DataColumn> 内のデータの列 (最終的には、そのテーブルに入力できるデータの種類を決定します) と、 <xref:System.Data.DataRow> 特定のテーブル内のデータ行を表します。 コントロールをデータテーブルに格納されている情報 (データテーブルへのコントロールのバインドなど) に複雑にバインドすることができ <xref:System.Windows.Forms.DataGridView> ます。 ただし、にバインドすると <xref:System.Data.DataTable> 、実際にはテーブルの既定のビューにバインドされます。  
  
- <xref:System.Data.DataView>. は、 <xref:System.Data.DataView> フィルター処理または並べ替えが可能な単一のデータテーブルのカスタマイズされたビューです。 データビューは、複合バインドコントロールによって使用されるデータ "スナップショット" です。 データビュー内のデータに単純バインドまたは複雑なバインドを行うことができますが、クリーンな更新データソースではなく、データの固定の "画像" にバインドすることに注意してください。  
  
- <xref:System.Data.DataSet>. <xref:System.Data.DataSet>は、データベース内のデータのテーブル、リレーションシップ、および制約のコレクションです。 データセット内のデータに単純バインドまたは複雑なバインドを行うことができますが、の既定のにバインドしている点に注意してください <xref:System.Data.DataViewManager> <xref:System.Data.DataSet> (次の箇条書きを参照してください)。  
  
- <xref:System.Data.DataViewManager>. は、に <xref:System.Data.DataViewManager> 似た全体のカスタマイズされたビューです <xref:System.Data.DataSet> が、リレーションシップが含まれてい <xref:System.Data.DataView> ます。 コレクションでは <xref:System.Data.DataViewManager.DataViewSettings%2A> 、が特定のテーブルに対して持つすべてのビューに対して、既定のフィルターおよび並べ替えオプションを設定でき <xref:System.Data.DataViewManager> ます。  
  
## <a name="see-also"></a>関連項目

- [Windows フォーム データ バインディングの変更通知](change-notification-in-windows-forms-data-binding.md)
- [データ連結と Windows フォーム](data-binding-and-windows-forms.md)
- [Windows フォームでのデータ バインディング](windows-forms-data-binding.md)
