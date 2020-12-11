---
title: DataGridView コントロールでの Just-in-time データ読み込みによる仮想モードの実装
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
ms.openlocfilehash: 5f1d3faad0bb05305086bc46076137f5b1202cb6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980659"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装

コントロールに仮想モードを実装する理由 <xref:System.Windows.Forms.DataGridView> の1つは、必要なときにのみデータを取得することです。 これは *just-in-time データ読み込み* と呼ばれます。  
  
 たとえば、リモートデータベースで非常に大きなテーブルを使用している場合は、ユーザーが新しい行をビューにスクロールしたときにのみ、表示および追加データを取得するために必要なデータのみを取得することで、起動の遅延を回避できます。 アプリケーションを実行しているクライアントコンピューターで、データの格納に使用できるメモリの量が限られている場合は、データベースから新しい値を取得するときに、未使用のデータを破棄することもできます。  
  
 次のセクションでは、just-in-time キャッシュでコントロールを使用する方法について説明し <xref:System.Windows.Forms.DataGridView> ます。  
  
 このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールで Just-in-time データ読み込みを使用して仮想モードを実装](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)する」を参照してください。  
  
## <a name="the-form"></a>フォーム  

 次のコード例では、 <xref:System.Windows.Forms.DataGridView> イベントハンドラーを通じてオブジェクトと対話する読み取り専用のコントロールを含むフォームを定義し `Cache` <xref:System.Windows.Forms.DataGridView.CellValueNeeded> ます。 オブジェクトは、 `Cache` ローカルに格納されている値を管理し、オブジェクトを使用して `DataRetriever` サンプル Northwind データベースの Orders テーブルから値を取得します。 `DataRetriever`クラスに必要なインターフェイスを実装するオブジェクトは、 `IDataPageRetriever` コントロールの `Cache` 行と列を初期化するためにも使用され <xref:System.Windows.Forms.DataGridView> ます。  
  
 `IDataPageRetriever`、 `DataRetriever` 、およびの各型について `Cache` は、このトピックの後半で説明します。  
  
> [!NOTE]
> 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>IDataPageRetriever インターフェイス  

 次のコード例では、 `IDataPageRetriever` クラスによって実装されるインターフェイスを定義し `DataRetriever` ます。 このインターフェイスで宣言されているメソッドは、 `SupplyPageOfData` 最初の行インデックスと1つのデータページの行数のカウントを必要とするメソッドだけです。 これらの値は、データソースからデータのサブセットを取得するために実装側によって使用されます。  
  
 オブジェクトは、 `Cache` 構築中にこのインターフェイスの実装を使用して、2つの初期ページのデータを読み込みます。 キャッシュされていない値が必要な場合、キャッシュはこれらのページのいずれかを破棄し、からの値を含む新しいページを要求し `IDataPageRetriever` ます。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>DataRetriever コンポーネントクラス  

 次のコード例では、 `DataRetriever` `IDataPageRetriever` サーバーからデータページを取得するためのインターフェイスを実装するクラスを定義しています。 クラスには、 `DataRetriever` プロパティとプロパティも用意されて `Columns` `RowCount` います。このプロパティは、コントロールがを使用して <xref:System.Windows.Forms.DataGridView> 必要な列を作成し、適切な数の空の行をコレクションに追加し <xref:System.Windows.Forms.DataGridView.Rows%2A> ます。 コントロールがテーブル内のすべてのデータを含んでいるかのように動作するように、空の行を追加する必要があります。 これは、スクロールバーのスクロールボックスが適切なサイズになり、ユーザーがテーブル内の任意の行にアクセスできるようになることを意味します。 行は、 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> スクロールして表示される場合にのみ、イベントハンドラーによって入力されます。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Cache クラス  

 次のコード例では、 `Cache` 実装を通じて設定される2ページのデータを管理するクラスを定義し `IDataPageRetriever` ます。 クラスは、 `Cache` `DataPage` <xref:System.Data.DataTable> 1 つのキャッシュページに値を格納し、ページの上限と下限を表す行インデックスを計算するを含む内部構造体を定義します。  
  
 クラスは、 `Cache` 構築時に2ページのデータを読み込みます。 イベントが <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 値を要求するたびに、オブジェクトは、その `Cache` 値が2つのページのいずれかで使用できるかどうかを判断し、存在する場合はそれを返します。 値がローカルで使用できない場合、 `Cache` オブジェクトは、現在表示されている行から最も遠い2つのページを特定し、そのページを要求された値を含む新しいページに置き換えます。  
  
 データページ内の行の数が、一度に画面に表示できる行数と同じであると仮定すると、このモデルでは、ユーザーがテーブルをページングして、最も最近表示されたページに効率的に戻ることができます。  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>その他の考慮事項  

 前のコード例は、just-in-time データ読み込みのデモとして提供されています。 最大限の効率を実現するには、独自のニーズに合わせてコードを変更する必要があります。 少なくとも、キャッシュ内のデータの1ページあたりの行数に適切な値を選択する必要があります。 この値は、コンストラクターに渡され `Cache` ます。 1ページあたりの行数は、コントロールに同時に表示できる行の数より少なくする必要があり <xref:System.Windows.Forms.DataGridView> ます。  
  
 最良の結果を得るには、パフォーマンステストとユーザビリティテストを実施して、システムとユーザーの要件を決定する必要があります。 考慮する必要がある要素には、アプリケーションを実行しているクライアントコンピューターのメモリの量、使用されるネットワーク接続の使用可能な帯域幅、および使用されるサーバーの待機時間などがあります。 帯域幅と待機時間は、ピーク時の使用時に決定する必要があります。  
  
 アプリケーションのスクロールパフォーマンスを向上させるために、ローカルに保存されるデータの量を増やすことができます。 ただし、起動時間を短縮するには、最初に大量のデータが読み込まれないようにする必要があります。 クラスを変更して、 `Cache` 格納できるデータページの数を増やすことができます。 より多くのデータページを使用すると、スクロール効率が向上しますが、使用可能な帯域幅とサーバーの待機時間によっては、データページ内の最適な行数を確認する必要があります。 ページ数を小さくすると、サーバーにはより頻繁にアクセスされますが、要求されたデータが返されるまでにかかる時間は短くなります。 待機時間が帯域幅よりも大きな問題である場合は、より大きなデータページを使用することをお勧めします。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Windows フォーム DataGridView コントロールでのパフォーマンス チューニング](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードを実装する](implementing-virtual-mode-wf-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールで Just-In-Time データ読み込みを使用して仮想モードを実装する](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
