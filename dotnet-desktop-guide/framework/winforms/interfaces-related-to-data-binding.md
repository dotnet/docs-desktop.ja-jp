---
title: データ連結に関連するインターフェイス
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 779b3f755d57014996af042d24236135293ce8ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983284"
---
# <a name="interfaces-related-to-data-binding"></a>データ連結に関連するインターフェイス

ADO.NET を使用すると、アプリケーションのバインドニーズと使用するデータに合わせて、さまざまなデータ構造を作成できます。 Windows フォームでデータを提供または使用するための独自のクラスを作成することもできます。 これらのオブジェクトは、基本的なデータ バインディングから、デザイン時サポートの提供、エラー チェック、変更通知、データ自体に加えられた変更の構造化されたロールバックのサポートに至るまで、さまざまなレベルの機能を提供することができ、複雑さに対応できます。

## <a name="consumers-of-data-binding-interfaces"></a>データ バインディング インターフェイスのコンシューマー

以下のセクションでは、インターフェイスオブジェクトの2つのグループについて説明します。 1 つ目のグループでは、データ ソース作成者がデータ ソースに実装するインターフェイスを示します。 これらのインターフェイスは、データ ソース コンシューマーが使用するように設計されています。ほとんどの場合、データ ソース コンシューマーは、Windows フォーム コントロールまたはコンポーネントです。 2 つ目のグループでは、コンポーネント作成者向けに設計されたインターフェイスを示します。 コンポーネント作成者は、Windows フォーム データ バインディング エンジンが使用する、データ バインディングをサポートするコンポーネントを作成するときにこれらのインターフェイスを使用します。 フォームに関連付けられたクラス内でこれらのインターフェイスを実装することで、データ バインディングを実現できます。各ケースは、データの操作を可能にするインターフェイスを実装するクラスを示しています。 Visual Studio の迅速なアプリケーション開発 (RAD) データデザインエクスペリエンスツールは、既にこの機能を利用しています。

### <a name="interfaces-for-implementation-by-data-source-authors"></a>データ ソース作成者が実装するインターフェイス

以下のインターフェイスは、Windows フォーム コントロールで使用するように設計されています。

- <xref:System.Collections.IList> インターフェイス

  インターフェイスを実装するクラスは <xref:System.Collections.IList> <xref:System.Array> 、、 <xref:System.Collections.ArrayList> 、または <xref:System.Collections.CollectionBase> です。 これらは、型の項目のインデックス付きリスト <xref:System.Object> です。 インデックスの最初の項目によって型が決定されるため、これらのリストには同種の型が含まれている必要があります。 <xref:System.Collections.IList> は、実行時にのみバインドに使用できます。

  > [!NOTE]
  > Windows フォームにバインドするビジネスオブジェクトの一覧を作成する場合は、を使用することを検討してください <xref:System.ComponentModel.BindingList%601> 。 <xref:System.ComponentModel.BindingList%601>は、双方向の Windows フォームデータバインディングに必要なプライマリインターフェイスを実装する拡張可能なクラスです。

- <xref:System.ComponentModel.IBindingList> インターフェイス

  インターフェイスを実装するクラスは、 <xref:System.ComponentModel.IBindingList> はるかに高いレベルのデータバインディング機能を提供します。 この実装では、基本的な並べ替え機能と変更通知を提供します。変更通知では、リスト項目が変更されたとき (たとえば、顧客リストの 3 番目の項目の Address フィールドが変更されたとき) と、リスト自体が変更されたとき (たとえば、リスト内の項目の数が増減したとき) のどちらの場合も変更が通知されます。 複数のコントロールを同じデータにバインドする予定であり、いずれかのコントロールで行われたデータ変更をバインドされた他のコントロールに反映させる必要がある場合に、変更通知が重要になります。

  > [!NOTE]
  > プロパティを使用してインターフェイスの変更通知を有効にし <xref:System.ComponentModel.IBindingList> <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> ます。このプロパティは、 `true` <xref:System.ComponentModel.IBindingList.ListChanged> リストが変更されたこと、またはリスト内の項目が変更されたことを示すイベントを発生させます。

  変更の種類は、パラメーターのプロパティによって記述され <xref:System.ComponentModel.ListChangedType> <xref:System.ComponentModel.ListChangedEventArgs> ます。 したがって、データ モデルが更新されるたびに、依存するビュー (同じデータ ソースにバインドされた他のコントロールなど) も更新されます。 ただし、一覧に含まれるオブジェクトは、リストがイベントを発生させることができるように、変更時にリストに通知する必要があり <xref:System.ComponentModel.IBindingList.ListChanged> ます。

  > [!NOTE]
  > は、 <xref:System.ComponentModel.BindingList%601> インターフェイスの一般的な実装を提供し <xref:System.ComponentModel.IBindingList> ます。

- <xref:System.ComponentModel.IBindingListView> インターフェイス

  インターフェイスを実装するクラスは <xref:System.ComponentModel.IBindingListView> 、の実装のすべての機能に <xref:System.ComponentModel.IBindingList> 加えて、フィルター処理や高度な並べ替え機能を提供します。 この実装では、文字列ベースのフィルター処理と、プロパティ記述子と方向のペアによる複数列の並べ替え機能を提供します。

- <xref:System.ComponentModel.IEditableObject> インターフェイス

  インターフェイスを実装するクラスを使用すると、オブジェクト <xref:System.ComponentModel.IEditableObject> に対する変更が永続的になるタイミングをオブジェクトで制御できます。 この実装では、、、およびの各メソッドを使用して、 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> オブジェクトに対して行われた変更をロールバックすることができます。 次に、、、およびの各メソッドの機能について簡単に説明 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> し、 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> データに加えられた変更をロールバックできるように、それらのメソッドを相互に連携させる方法を示します。

  - メソッドは、 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> オブジェクトに対する編集の開始を通知します。 このインターフェイスを実装するオブジェクトは、メソッド <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> が呼び出された場合に更新を破棄できるように、メソッド呼び出しの後に更新を保存する必要があり <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> ます。 データバインディング Windows フォームでは、 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 1 つの編集トランザクションのスコープ内でを複数回呼び出すことができます (たとえば、、 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 、 <xref:System.ComponentModel.IEditableObject.EndEdit%2A> )。 の実装 <xref:System.ComponentModel.IEditableObject> で <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> は、が既に呼び出されているかどうかを追跡し、後続のへの呼び出しを無視する必要があり <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> ます。 このメソッドは複数回呼び出すことができるので、それ以降の呼び出しは破壊的であることが重要です。つまり、それ以降の呼び出しでは、 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 作成された更新を破棄したり、最初の呼び出しで保存されたデータを変更したりすることはできません <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 。

  - <xref:System.ComponentModel.IEditableObject.EndEdit%2A> <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> オブジェクトが現在編集モードである場合、メソッドは、が呼び出されてから基になるオブジェクトに変更をプッシュします。

  - メソッドは、 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> オブジェクトに対して行われたすべての変更を破棄します。

  、、およびの各メソッドの動作の詳細については、 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 「 [データベースにデータを保存する](/visualstudio/data-tools/save-data-back-to-the-database)」を参照してください。

  このトランザクションのデータ機能の概念は、コントロールによって使用され <xref:System.Windows.Forms.DataGridView> ます。

- <xref:System.ComponentModel.ICancelAddNew> インターフェイス

  インターフェイスを実装するクラスは、 <xref:System.ComponentModel.ICancelAddNew> 通常、 <xref:System.ComponentModel.IBindingList> インターフェイスを実装し、メソッドを使用してデータソースに加えられた追加をロールバックすることができ <xref:System.ComponentModel.IBindingList.AddNew%2A> ます。 データソースがインターフェイスを実装している場合は <xref:System.ComponentModel.IBindingList> 、インターフェイスも実装する必要があり <xref:System.ComponentModel.ICancelAddNew> ます。

- <xref:System.ComponentModel.IDataErrorInfo> インターフェイス

  インターフェイスを実装するクラスを使用すると、オブジェクトは、バインドされた <xref:System.ComponentModel.IDataErrorInfo> コントロールにカスタムエラー情報を提供できます。

  - プロパティは、 <xref:System.ComponentModel.IDataErrorInfo.Error%2A> 一般的なエラーメッセージテキスト ("エラーが発生しました" など) を返します。

  - プロパティは、 <xref:System.ComponentModel.IDataErrorInfo.Item%2A> 列からの特定のエラーメッセージを含む文字列を返します ("列の値 `State` が無効です" など)。

- <xref:System.Collections.IEnumerable> インターフェイス

  インターフェイスを実装するクラス <xref:System.Collections.IEnumerable> は、通常、ASP.NET によって使用されます。 このインターフェイスの Windows フォームサポートは、コンポーネントを通じてのみ使用でき <xref:System.Windows.Forms.BindingSource> ます。

  > [!NOTE]
  > コンポーネントは、 <xref:System.Windows.Forms.BindingSource> <xref:System.Collections.IEnumerable> バインドのためにすべての項目を別のリストにコピーします。

- <xref:System.ComponentModel.ITypedList> インターフェイス

  インターフェイスを実装するコレクションクラスは、 <xref:System.ComponentModel.ITypedList> バインドされたコントロールに公開されるプロパティの順序とセットを制御する機能を提供します。

  > [!NOTE]
  > メソッドを実装し、 <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> <xref:System.ComponentModel.PropertyDescriptor> 配列が null でない場合、配列の最後のエントリは、項目の別のリストであるリストプロパティを記述するプロパティ記述子になります。

- <xref:System.ComponentModel.ICustomTypeDescriptor> インターフェイス

  インターフェイスを実装するクラスは、 <xref:System.ComponentModel.ICustomTypeDescriptor> それ自体に関する動的な情報を提供します。 このインターフェイスはに似 <xref:System.ComponentModel.ITypedList> ていますが、リストではなくオブジェクトに使用されます。 このインターフェイスは、 <xref:System.Data.DataRowView> 基になる行のスキーマを射影するために、によって使用されます。 の単純な実装 <xref:System.ComponentModel.ICustomTypeDescriptor> は、クラスによって提供され <xref:System.ComponentModel.CustomTypeDescriptor> ます。

  > [!NOTE]
  > を実装する型へのデザイン時バインディングをサポートするには、 <xref:System.ComponentModel.ICustomTypeDescriptor> 型もを実装し、フォームのインスタンスとして存在する必要があり <xref:System.ComponentModel.IComponent> ます。

- <xref:System.ComponentModel.IListSource> インターフェイス

  インターフェイスを実装するクラスは、 <xref:System.ComponentModel.IListSource> リスト以外のオブジェクトのリストベースのバインドを有効にします。 <xref:System.ComponentModel.IListSource.GetList%2A>のメソッド <xref:System.ComponentModel.IListSource> は、を継承しないオブジェクトからバインド可能なリストを返すために使用され <xref:System.Collections.IList> ます。 <xref:System.ComponentModel.IListSource> は、クラスによって使用され <xref:System.Data.DataSet> ます。

- <xref:System.ComponentModel.IRaiseItemChangedEvents> インターフェイス

  インターフェイスを実装するクラス <xref:System.ComponentModel.IRaiseItemChangedEvents> は、インターフェイスも実装するバインド可能なリストです <xref:System.ComponentModel.IBindingList> 。 このインターフェイスは、型が <xref:System.ComponentModel.IBindingList.ListChanged> プロパティを通じて型のイベントを発生させるかどうかを示すために使用され <xref:System.ComponentModel.ListChangedType.ItemChanged> <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> ます。

  > [!NOTE]
  > <xref:System.ComponentModel.IRaiseItemChangedEvents>前に説明したイベント変換を一覧表示し、コンポーネントと対話するプロパティがデータソースに用意されている場合は、を実装する必要があり <xref:System.Windows.Forms.BindingSource> ます。 それ以外の場合、では、 <xref:System.Windows.Forms.BindingSource> イベント変換の一覧を表示するプロパティも実行され、パフォーマンスが低下します。

- <xref:System.ComponentModel.ISupportInitialize> インターフェイス

  インターフェイスを実装するコンポーネントには、 <xref:System.ComponentModel.ISupportInitialize> プロパティの設定や共同依存プロパティの初期化のためのバッチ最適化の利点があります。 には、 <xref:System.ComponentModel.ISupportInitialize> 次の2つのメソッドがあります。

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> オブジェクトの初期化が開始されていることを通知します。

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> オブジェクトの初期化が完了していることを通知します。

- <xref:System.ComponentModel.ISupportInitializeNotification> インターフェイス

  インターフェイスを実装するコンポーネント <xref:System.ComponentModel.ISupportInitializeNotification> もインターフェイスを実装し <xref:System.ComponentModel.ISupportInitialize> ます。 このインターフェイスを使用すると、 <xref:System.ComponentModel.ISupportInitialize> 初期化が完了したことを他のコンポーネントに通知できます。 インターフェイスには、 <xref:System.ComponentModel.ISupportInitializeNotification> 次の2つのメンバーが含まれます。

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>`boolean`コンポーネントが初期化されているかどうかを示す値を返します。

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> が呼び出されたときに発生し <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> ます。

- <xref:System.ComponentModel.INotifyPropertyChanged> インターフェイス

  このインターフェイスを実装するクラスは、プロパティ値のいずれかが変更されたときにイベントを発生させる型です。 このインターフェイスは、コントロールのプロパティごとに変更イベントを持つパターンを置き換えるように設計されています。 で使用する場合 <xref:System.ComponentModel.BindingList%601> 、ビジネスオブジェクトはインターフェイスを実装する必要があり、 <xref:System.ComponentModel.INotifyPropertyChanged> BindingList \` 1 は <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> イベントを <xref:System.ComponentModel.BindingList%601.ListChanged> 型のイベントに変換し <xref:System.ComponentModel.ListChangedType.ItemChanged> ます。

  > [!NOTE]
  > バインドされたクライアントとデータソースの間のバインディングで変更通知が発生するようにするには、バインドされたデータソースの型でインターフェイスを実装するか <xref:System.ComponentModel.INotifyPropertyChanged> (推奨)、バインドされた型に *propertyName* イベントを指定し `Changed` ますが、両方を実行しないようにします。

### <a name="interfaces-for-implementation-by-component-authors"></a>コンポーネント作成者が実装するインターフェイス

以下のインターフェイスは、Windows フォーム データ バインディング エンジンが使用するように設計されています。

- <xref:System.Windows.Forms.IBindableComponent> インターフェイス

  このインターフェイスを実装するクラスは、データ バインディングをサポートするコントロール以外のコンポーネントです。 このクラスは、 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> このインターフェイスのプロパティとプロパティを使用して、コンポーネントのデータバインディングとバインディングコンテキストを返し <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> ます。

  > [!NOTE]
  > コンポーネントがから継承している場合は、 <xref:System.Windows.Forms.Control> インターフェイスを実装する必要はありません <xref:System.Windows.Forms.IBindableComponent> 。

- <xref:System.Windows.Forms.ICurrencyManagerProvider> インターフェイス

  インターフェイスを実装するクラス <xref:System.Windows.Forms.ICurrencyManagerProvider> は、 <xref:System.Windows.Forms.CurrencyManager> この特定のコンポーネントに関連付けられているバインディングを管理するための独自のを提供するコンポーネントです。 カスタムへのアクセス <xref:System.Windows.Forms.CurrencyManager> は、プロパティによって提供され <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> ます。

  > [!NOTE]
  > を継承するクラスは、 <xref:System.Windows.Forms.Control> プロパティを通じてバインドを自動的に管理し <xref:System.Windows.Forms.Control.BindingContext%2A> ます。そのため、を実装する必要がある場合 <xref:System.Windows.Forms.ICurrencyManagerProvider> は、非常にまれです。

## <a name="see-also"></a>関連項目

- [データ連結と Windows フォーム](data-binding-and-windows-forms.md)
- [方法: Windows フォームに単純バインド コントロールを作成する](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Windows フォームでのデータ バインディング](windows-forms-data-binding.md)
