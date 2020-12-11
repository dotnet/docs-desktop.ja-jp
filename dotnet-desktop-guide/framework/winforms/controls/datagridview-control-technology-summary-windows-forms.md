---
title: DataGridView コントロール テクノロジの概要
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 1b620cabb756fadb8468fc75879025131e4bffd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974208"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>DataGridView コントロール テクノロジの概要 (Windows フォーム)

ここでは、`DataGridView` コントロールおよびその使用をサポートしているクラスの概要について説明します。  
  
 表形式でのデータの表示は、頻繁に実行されるタスクです。 この `DataGridView` コントロールは、グリッドにデータを表示するための完全なソリューションとして設計されています。  
  
## <a name="keywords"></a>キーワード  

 DataGridView、BindingSource、テーブル、セル、データバインディング、仮想モード  
  
## <a name="namespaces"></a>名前空間  

 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>関連テクノロジ  

 `BindingSource`  
  
## <a name="background"></a>バックグラウンド  

 ユーザーインターフェイス (UI) デザイナーでは、表形式のデータをユーザーに表示するために必要となることがよくあります。 .NET Framework には、テーブルまたはグリッドにデータを表示するいくつかの方法が用意されています。 コントロールは、 `DataGridView` Windows フォームアプリケーションのこのテクノロジの最新の進化を表します。  
  
 コントロールは、 `DataGridView` データストアのデータ行を表示できます。 多くの種類のデータストアがサポートされています。 データストアは、1次元配列などの単純な型指定されていないデータを保持することも、などの型指定されたデータを保持することもでき <xref:System.Data.DataSet> ます。 詳細については、「 [方法: データを Windows フォーム DataGridView コントロールにバインドする](how-to-bind-data-to-the-windows-forms-datagridview-control.md)」を参照してください。  
  
 `DataGridView` コントロールには、データを表形式で表示するための強力で柔軟な機能が用意されています。 コントロールを使用すると、サイズが非常に大きいデータセットの読み取り専用または編集可能なビューを表示できます。  
  
 `DataGridView`さまざまな方法でコントロールを拡張して、アプリケーションにカスタム動作を組み込むことができます。 たとえば、プログラムで独自の並べ替えアルゴリズムを指定したり、独自の種類のセルを作成したりできます。 `DataGridView` コントロールの外観は、いくつかのプロパティを選択することで簡単にカスタマイズできます。 データストアの種類によっては、データソースとして使用することができます。また、データソースがバインドされていなくても、 `DataGridView` コントロールを操作できます。  
  
## <a name="implementing-datagridview-classes"></a>DataGridView クラスの実装  

 コントロールの機能拡張機能を利用するには、いくつかの方法があり `DataGridView` ます。 イベントとプロパティを使用してコントロールのさまざまな側面をカスタマイズできますが、一部のカスタマイズでは、既存のクラスから派生した新しいクラスを作成する必要があり `DataGridView` ます。  
  
 最も一般的に使用される基底クラスは、 `DataGridViewCell` および `DataGridViewColumn` です。 独自の cell クラス `DataGridViewCell` は、またはその子クラスから派生させることができます。 任意のセル型を任意の列に追加できますが、 `DataGridViewColumn` 既定では、カスタムセル型のセルをホストするのコンパニオン列クラスも派生します。  
  
 `IDataGridViewEditingCell`派生セルクラスにインターフェイスを実装して、編集機能を持つセル型を作成できますが、編集モードではコントロールをホストしません。 編集モードのセルでホストできるコントロールを作成するには、 `IDataGridViewEditingControl` から派生したクラスにインターフェイスを実装し <xref:System.Windows.Forms.Control> ます。  
  
 詳細については、「 [方法: 動作と外観を拡張して Windows フォーム Datagridview コントロールのセルと列をカスタマイズ](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) する」および「 [方法: Windows フォーム Datagridview セルのコントロールをホストする](how-to-host-controls-in-windows-forms-datagridview-cells.md)」を参照してください。  
  
## <a name="datagridview-classes-at-a-glance"></a>DataGridView クラスの概要  

 <xref:System.Windows.Forms>  
  
|テクノロジ領域|クラス/インターフェイス/構成要素|  
|---------------------|-------------------------------------------------|  
|データ バインディング|<xref:System.Windows.Forms.BindingSource>|  
|データプレゼンテーション|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> および派生クラス<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> および派生クラス<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> および派生クラス<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> 拡張性|<xref:System.Windows.Forms.DataGridViewCell> および派生クラス<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> および派生クラス<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>新機能  

 この <xref:System.Windows.Forms.DataGridView> コントロールは、Windows フォームで表形式のデータを表示するための完全なソリューションとして設計されています。 <xref:System.Windows.Forms.DataGridView>新しいアプリケーションを作成する場合は、などの他のソリューションの前に、コントロールを使用することを検討してください <xref:System.Windows.Forms.DataGrid> 。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。  
  
 <xref:System.Windows.Forms.DataGridView>コントロールは、コンポーネントと密接に連携することができ <xref:System.Windows.Forms.BindingSource> ます。 このコンポーネントは、フォームのプライマリデータソースとして設計されています。 <xref:System.Windows.Forms.DataGridView>データソースの種類に関係なく、コントロールとそのデータソース間の相互作用を管理できます。  
  
## <a name="see-also"></a>関連項目

- [DataGridView コントロールの概要](datagridview-control-overview-windows-forms.md)
- [DataGridView コントロールのアーキテクチャ](datagridview-control-architecture-windows-forms.md)
- [接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)
