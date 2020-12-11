---
title: BindingSource コンポーネント アーキテクチャ
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975118"
---
# <a name="bindingsource-component-architecture"></a>BindingSource コンポーネント アーキテクチャ
コンポーネントを使用すると <xref:System.Windows.Forms.BindingSource> 、すべての Windows フォームコントロールをデータソースにユニバーサルにバインドできます。  
  
 <xref:System.Windows.Forms.BindingSource>コンポーネントを使用すると、コントロールをデータソースにバインドするプロセスが簡略化され、従来のデータバインドよりも次のような利点があります。  
  
- ビジネスオブジェクトに対するデザイン時のバインドを有効にします。  
  
- <xref:System.Windows.Forms.CurrencyManager>機能をカプセル化し、 <xref:System.Windows.Forms.CurrencyManager> デザイン時にイベントを公開します。  
  
- <xref:System.ComponentModel.IBindingList>リスト変更通知をネイティブでサポートしていないデータソースに対してリスト変更通知を提供することにより、インターフェイスをサポートするリストの作成を簡略化します。  
  
- メソッドの機能拡張ポイントを提供 <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> します。  
  
- データソースとコントロールの間に間接的なレベルの間接参照を提供します。 この間接参照は、データソースが実行時に変更される可能性がある場合に重要です。  
  
- 他のデータ関連の Windows フォームコントロール、特におよびコントロールと相互運用し <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.DataGridView> ます。  
  
 このような理由から、 <xref:System.Windows.Forms.BindingSource> Windows フォームコントロールをデータソースにバインドするには、コンポーネントを使用することをお勧めします。  
  
## <a name="bindingsource-features"></a>BindingSource の機能  
 <xref:System.Windows.Forms.BindingSource>コンポーネントには、コントロールをデータにバインドするための機能がいくつか用意されています。 これらの機能を使用すると、ほとんどのコーディングを行わずにほとんどのデータバインディングシナリオを実装できます。  
  
 コンポーネントは、さまざま <xref:System.Windows.Forms.BindingSource> な種類のデータソースにアクセスするための一貫したインターフェイスを提供することによってこれを実現します。 これは、任意の型へのバインドに同じ手順を使用することを意味します。 たとえば、プロパティをまたはビジネスオブジェクトにアタッチすることができ、どちらの場合も、 <xref:System.Windows.Forms.BindingSource.DataSource%2A> <xref:System.Data.DataSet> 同じプロパティ、メソッド、およびイベントのセットを使用してデータソースを操作します。  
  
 コンポーネントによって提供される一貫したインターフェイスにより、 <xref:System.Windows.Forms.BindingSource> データをコントロールにバインドするプロセスが大幅に簡略化されます。 変更通知を提供するデータソースの種類の場合、 <xref:System.Windows.Forms.BindingSource> コンポーネントはコントロールとデータソースの間の変更を自動的に伝達します。 変更通知を提供しないデータソースの種類の場合、変更通知を発生させるためのイベントが提供されます。 次の一覧に、コンポーネントでサポートされる機能を示し <xref:System.Windows.Forms.BindingSource> ます。  
  
- 演算.  
  
- 通貨管理。  
  
- リストとしてのデータソース。  
  
- <xref:System.Windows.Forms.BindingSource> として <xref:System.ComponentModel.IBindingList> 。  
  
- カスタム項目の作成。  
  
- トランザクション項目の作成。  
  
- <xref:System.Collections.IEnumerable> ご.  
  
- デザイン時サポート。  
  
- 静的 <xref:System.Windows.Forms.ListBindingHelper> メソッド。  
  
- インターフェイスを使用した並べ替えとフィルター処理 <xref:System.ComponentModel.IBindingListView> 。  
  
- との統合 <xref:System.Windows.Forms.BindingNavigator> 。  
  
### <a name="indirection"></a>間接  
 コンポーネントは、 <xref:System.Windows.Forms.BindingSource> コントロールとデータソースの間に間接的なレベルの間接参照を提供します。 コントロールをデータソースに直接バインドするのではなく、コントロールをにバインド <xref:System.Windows.Forms.BindingSource> し、コンポーネントのプロパティにデータソースをアタッチし <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.DataSource%2A> ます。  
  
 このレベルの間接参照を使用すると、コントロールバインドをリセットせずにデータソースを変更できます。 これにより、次の機能が提供されます。  
  
- <xref:System.Windows.Forms.BindingSource>現在のコントロールバインドを保持したまま、を別のデータソースにアタッチできます。  
  
- データソース内の項目を変更し、バインドされたコントロールに通知できます。 詳細については、「 [方法: BindingSource を使用して Windows フォームコントロールにデータソースの更新を反映させる](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)」を参照してください。  
  
- メモリ内のオブジェクトの代わりに、にバインドでき <xref:System.Type> ます。 詳細については、「 [方法: Windows フォームコントロールを型にバインドする](how-to-bind-a-windows-forms-control-to-a-type.md)」を参照してください。 その後、実行時にオブジェクトにバインドできます。  
  
### <a name="currency-management"></a>通貨管理  
 コンポーネントは、 <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.ICurrencyManagerProvider> 通貨管理を処理するためのインターフェイスを実装します。 インターフェイスを使用すると、 <xref:System.Windows.Forms.ICurrencyManagerProvider> 同じにバインドされている別の通貨マネージャーに加えて、の通貨マネージャーにアクセスすることもでき <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.DataMember%2A> ます。  
  
 コンポーネントには、 <xref:System.Windows.Forms.BindingSource> 機能がカプセル化され <xref:System.Windows.Forms.CurrencyManager> ており、最も一般的なプロパティとイベントが公開されて <xref:System.Windows.Forms.CurrencyManager> います。 次の表では、通貨管理に関連する一部のメンバーについて説明します。  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> プロパティ  
 に関連付けられている通貨マネージャーを取得し <xref:System.Windows.Forms.BindingSource> ます。  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A> メソッド  
 <xref:System.Windows.Forms.BindingSource>指定されたデータメンバーに別のバインドがある場合は、その通貨マネージャーを取得します。  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> プロパティ  
 データソースの現在の項目を取得します。  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> プロパティ  
 基になるリストでの現在の位置を取得または設定します。  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> メソッド  
 基になるデータ ソースに保留中の変更を適用します。  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> メソッド  
 現在の編集操作をキャンセルします。  
  
### <a name="data-source-as-a-list"></a>リストとしてのデータソース  
 コンポーネントは、 <xref:System.Windows.Forms.BindingSource> <xref:System.ComponentModel.IBindingListView> インターフェイスとインターフェイスを実装し <xref:System.ComponentModel.ITypedList> ます。 この実装では、 <xref:System.Windows.Forms.BindingSource> 外部ストレージを使用せずに、コンポーネント自体をデータソースとして使用できます。  
  
 <xref:System.Windows.Forms.BindingSource>コンポーネントがデータソースにアタッチされると、データソースがリストとして公開されます。  
  
 プロパティは、 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 複数のデータソースに設定できます。 これには、型、オブジェクト、および型のリストが含まれます。 結果として得られるデータソースはリストとして公開されます。 次の表は、いくつかの一般的なデータソースと結果の一覧の評価を示しています。  
  
|DataSource プロパティ|結果の一覧表示|  
|-------------------------|------------------|  
|null 参照 (Visual Basic の場合は `Nothing`)。|<xref:System.ComponentModel.IBindingList>オブジェクトの空の。 項目を追加すると、追加した項目の種類にリストが設定されます。|  
|`Nothing`Set を使用した null 参照 (Visual Basic) <xref:System.Windows.Forms.BindingSource.DataMember%2A>|サポートされていません。を発生させ <xref:System.ArgumentException> ます。|  
|非リスト型または型 "T" のオブジェクト|<xref:System.ComponentModel.IBindingList>型 "T" の空の。|  
|配列インスタンス|<xref:System.ComponentModel.IBindingList>配列要素を格納している。|  
|<xref:System.Collections.IEnumerable> instance|<xref:System.ComponentModel.IBindingList>項目を格納している。 <xref:System.Collections.IEnumerable>|  
|型 "T" を含むリストインスタンス|<xref:System.ComponentModel.IBindingList>型 "T" を格納しているインスタンス。|  
  
 また、は、 <xref:System.Windows.Forms.BindingSource.DataSource%2A> やなどの他の種類のリストにも設定でき、では <xref:System.ComponentModel.IListSource> 適切に <xref:System.ComponentModel.ITypedList> <xref:System.Windows.Forms.BindingSource> 処理されます。 この場合、リストに含まれる型には、パラメーターなしのコンストラクターが必要です。  
  
### <a name="bindingsource-as-an-ibindinglist"></a>IBindingList としての BindingSource  
 コンポーネントには、 <xref:System.Windows.Forms.BindingSource> 基になるデータにアクセスして操作するためのメンバーが用意されて <xref:System.ComponentModel.IBindingList> います。 次の表では、これらのメンバーの一部について説明します。  
  
|メンバー|説明|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> プロパティ|プロパティまたはプロパティの評価の結果として得られるリストを取得し <xref:System.Windows.Forms.BindingSource.DataSource%2A> <xref:System.Windows.Forms.BindingSource.DataMember%2A> ます。|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> メソッド|基になるリストに新しい項目を追加します。 インターフェイスを実装 <xref:System.ComponentModel.IBindingList> し、項目の追加を許可する (つまり、プロパティがに設定されている) データソースに適用さ <xref:System.Windows.Forms.BindingSource.AllowNew%2A> `true` れます。|  
  
### <a name="custom-item-creation"></a>カスタム項目の作成  
 イベントを処理し <xref:System.Windows.Forms.BindingSource.AddingNew> て、独自の項目作成ロジックを提供できます。 <xref:System.Windows.Forms.BindingSource.AddingNew>イベントは、に新しいオブジェクトが追加される前に発生し <xref:System.Windows.Forms.BindingSource> ます。 このイベントは、 <xref:System.Windows.Forms.BindingSource.AddNew%2A> メソッドが呼び出された後、新しい項目が基になるリストに追加される前に発生します。 このイベントを処理することにより、クラスから派生せずにカスタムの項目作成動作を提供でき <xref:System.Windows.Forms.BindingSource> ます。 詳細については、「 [方法: Windows フォーム BindingSource を使用して項目の追加をカスタマイズする](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)」を参照してください。  
  
### <a name="transactional-item-creation"></a>トランザクション項目の作成  
 コンポーネントは、 <xref:System.Windows.Forms.BindingSource> <xref:System.ComponentModel.ICancelAddNew> トランザクションアイテムの作成を可能にするインターフェイスを実装します。 の呼び出しを使用して新しい項目を仮に作成した後は、 <xref:System.Windows.Forms.BindingSource.AddNew%2A> 次の方法で追加をコミットまたはロールバックできます。  
  
- <xref:System.ComponentModel.ICancelAddNew.EndNew%2A>メソッドは、保留中の加算を明示的にコミットします。  
  
- 挿入、削除、移動などの別のコレクション操作を実行すると、保留中の追加が暗黙的にコミットされます。  
  
- メソッドが <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> まだコミットされていない場合、メソッドは保留中の加算をロールバックします。  
  
### <a name="ienumerable-support"></a>IEnumerable のサポート  
 <xref:System.Windows.Forms.BindingSource>コンポーネントにより、データソースへのバインドコントロールが有効になり <xref:System.Collections.IEnumerable> ます。 このコンポーネントを使用すると、などのデータソースにバインドでき <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType> ます。  
  
 <xref:System.Collections.IEnumerable>データソースがコンポーネントに割り当てられると、によって <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource> が作成され、 <xref:System.ComponentModel.IBindingList> データソースの内容がリストに追加され <xref:System.Collections.IEnumerable> ます。  
  
### <a name="design-time-support"></a>Design-Time サポート  
 ファクトリクラスから作成されたオブジェクトや Web サービスによって返されるオブジェクトなど、デザイン時に作成できないオブジェクトの種類もあります。 コントロールをバインドできるメモリ内にオブジェクトがない場合でも、デザイン時にコントロールをこれらの型にバインドすることが必要になることがあります。 たとえば、コントロールの列ヘッダーに <xref:System.Windows.Forms.DataGridView> カスタム型のパブリックプロパティの名前を付ける必要がある場合があります。  
  
 このシナリオをサポートするために、 <xref:System.Windows.Forms.BindingSource> コンポーネントはへのバインドをサポートして <xref:System.Type> います。 をプロパティに割り当てると、コンポーネントによっ <xref:System.Type> <xref:System.Windows.Forms.BindingSource.DataSource%2A> て <xref:System.Windows.Forms.BindingSource> 空の項目が作成され <xref:System.ComponentModel.BindingList%601> <xref:System.Type> ます。 その後、コンポーネントにバインドするコントロール <xref:System.Windows.Forms.BindingSource> は、デザイン時または実行時に型のプロパティまたはスキーマの存在について警告されます。 詳細については、「 [方法: Windows フォームコントロールを型にバインドする](how-to-bind-a-windows-forms-control-to-a-type.md)」を参照してください。  
  
### <a name="static-listbindinghelper-methods"></a>静的 ListBindingHelper メソッド  
 <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>、 <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType> 、および <xref:System.Windows.Forms.BindingSource> 型はすべて、ペアからリストを生成するための共通のロジックを共有し `DataSource` / `DataMember` ます。 また、この共通のロジックは、次の方法でコントロールの作成者や他のサードパーティが使用するために公開されてい `static` ます。  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>IBindingListView インターフェイスを使用した並べ替えとフィルター処理  
 コンポーネントは、インターフェイスを <xref:System.Windows.Forms.BindingSource> <xref:System.ComponentModel.IBindingListView> 拡張するインターフェイスを実装し <xref:System.ComponentModel.IBindingList> ます。 では、 <xref:System.ComponentModel.IBindingList> 単一列の並べ替えと、による <xref:System.ComponentModel.IBindingListView> 高度な並べ替えとフィルター処理が提供されています。 では <xref:System.ComponentModel.IBindingListView> 、データソースがこれらのインターフェイスのいずれかを実装している場合に、データソース内の項目の並べ替えとフィルター処理を行うことができます。 コンポーネントには、 <xref:System.Windows.Forms.BindingSource> これらのメンバーの参照実装が用意されていません。 代わりに、呼び出しが基になるリストに転送されます。  
  
 次の表では、並べ替えとフィルター処理に使用するプロパティについて説明します。  
  
|メンバー|説明|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> プロパティ|データ ソースが <xref:System.ComponentModel.IBindingListView> である場合は、表示する行のフィルター処理に使用する式を取得または設定します。|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> プロパティ|データ ソースが <xref:System.ComponentModel.IBindingList> である場合は、並べ替えに使用する列名と並べ替え順序情報を取得または設定します。<br /><br /> または<br /><br /> データソースがで、 <xref:System.ComponentModel.IBindingListView> 高度な並べ替えをサポートしている場合、並べ替えと並べ替えの順序に使用される複数の列名を取得します。|  
  
### <a name="integration-with-bindingnavigator"></a>BindingNavigator との統合  
 コンポーネントを使用すると、 <xref:System.Windows.Forms.BindingSource> 任意の Windows フォームコントロールをデータソースにバインドできますが、 <xref:System.Windows.Forms.BindingNavigator> コントロールは特にコンポーネントを操作するように設計されてい <xref:System.Windows.Forms.BindingSource> ます。 コントロールには、 <xref:System.Windows.Forms.BindingNavigator> コンポーネントの現在の項目を制御するためのユーザーインターフェイスが用意されて <xref:System.Windows.Forms.BindingSource> います。 既定では、コントロールには、 <xref:System.Windows.Forms.BindingNavigator> コンポーネントのナビゲーションメソッドに対応するボタンが用意されて <xref:System.Windows.Forms.BindingSource> います。 詳細については、「 [方法: Windows フォーム BindingNavigator コントロールを使用してデータを移動する](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [BindingSource コンポーネントの概要](bindingsource-component-overview.md)
- [BindingNavigator コントロール](bindingnavigator-control-windows-forms.md)
- [Windows フォームでのデータ バインディング](../windows-forms-data-binding.md)
- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
- [方法: Windows フォーム コントロールを型にバインドする](how-to-bind-a-windows-forms-control-to-a-type.md)
- [方法: BindingSource を使用して Windows フォーム コントロール内にデータ ソースの更新を反映させる](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
