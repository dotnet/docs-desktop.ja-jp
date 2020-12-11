---
title: 既定の XAML スキーマ コンテキストと WPF XAML スキーマ コンテキスト
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985756"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>既定の XAML スキーマ コンテキストと WPF XAML スキーマ コンテキスト
XAML スキーマコンテキストは、特定の XAML ボキャブラリを使用する XAML 運用がオブジェクト書き込み動作とどのようにやり取りするかを示す概念エンティティです。これには、型マッピングの解決方法、アセンブリの読み込み方法、特定のリーダーとライターの設定の解釈方法などが含まれます。 このトピックでは、CLR 型システムに基づく .NET XAML サービスと、関連付けられた既定の XAML スキーマコンテキストの機能について説明します。 このトピックでは、WPF に使用される XAML スキーマコンテキストについても説明します。

## <a name="default-xaml-schema-context"></a>既定の XAML スキーマコンテキスト

.NET XAML サービスは、既定の XAML スキーマコンテキストを実装し、使用します。 既定の XAML スキーマコンテキストの動作は、クラスの API では常に完全に表示されるとは限りません <xref:System.Xaml.XamlSchemaContext> 。 ただし、多くの場合、既定の XAML スキーマコンテキストによって影響を受ける動作は、XAML 型システムの共通の API (またはのメンバー)、 <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlType> または既定の xaml スキーマコンテキストを使用する xaml リーダーおよび xaml ライターで公開されている api を使用して監視できます。

<xref:System.Xaml.XamlSchemaContext>コンストラクターを呼び出すことによって、既定の動作をカプセル化するを作成でき <xref:System.Xaml.XamlSchemaContext> ます。 これにより、既定の XAML スキーマコンテキストが明示的に作成されます。 入力パラメーターを明示的に受け取らない Api を使用して XAML リーダーまたは XAML ライターを初期化すると、同じ既定の XAML スキーマコンテキストが暗黙的に作成され <xref:System.Xaml.XamlSchemaContext> ます。

既定の XAML スキーマコンテキストは、その型マッピング動作の CLR リフレクションに依存しています。 これには、CLR を定義すること、 <xref:System.Type> および関連するまたはを調べることが含まれ <xref:System.Reflection.PropertyInfo> <xref:System.Reflection.MethodInfo> ます。 また、型またはメンバーの CLR 属性は、CLR バッキング型を使用する XAML 型または XAML メンバー情報の詳細を入力するために使用されます。 既定の XAML スキーマコンテキストには、 `Invoker` CLR 型システムから必要な情報を取得できるため、パターンなどの型システム拡張手法は必要ありません。

アセンブリ読み込みロジックの場合、既定の XAML スキーマコンテキストは、主に XAML 名前空間マッピングで提供されるアセンブリ値に依存します。 また、は、 <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> 内部型の読み込みなどのシナリオで、読み込むアセンブリをヒントにすることができます。

## <a name="wpf-xaml-schema-context"></a>WPF XAML スキーマコンテキスト

Wpf XAML スキーマコンテキストについては、このトピックで説明します。これは、WPF の実装により、既定以外の XAML スキーマコンテキストを実装することによって導入できる機能の種類がわかりやすく示されているためです。 また、XAML スキーマコンテキストの概念は、wpf の XAML に関連する WPF ドキュメントではあまり詳しく説明されていません。XAML スキーマコンテキストが有効になっている動作は、既定の XAML スキーマコンテキストがどのように動作するかについての説明と統合している場合にのみ、完全に理解できることがあります。 WPF XAML スキーマコンテキストは、次の動作を実装します。

**参照の上書き:** WPF には、XAML 用のいくつかのコンテンツモデルがあります。この場合、属性が指定されていない XAML コンテンツプロパティが存在 <xref:System.Windows.Markup.ContentPropertyAttribute> します。 <xref:System.Xaml.XamlType.LookupContentProperty%2A> WPF のオーバーライドは、この動作を実装します。

**WPF 式の遅延:** WPF では、ランタイムコンテキストが使用可能になるまで値を遅延させるいくつかの式クラスが機能します。 また、テンプレートの拡張は、遅延手法に依存するランタイム動作です。

**型システム参照の最適化:** WPF には、さまざまな XAML ボキャブラリとオブジェクトモデルがあります。これには、文字どおり数百の WPF 定義クラスに継承する基底クラスメンバー定義が含まれます。 また、WPF 自体は複数のアセンブリにわたって分散されています。 WPF では、参照テーブルやその他の手法を使用して、その型の参照を最適化します。 これにより、既定の XAML スキーマコンテキストと CLR ベースの型参照よりもパフォーマンスが向上します。 参照テーブルに型が存在しない場合、この動作は、既定の XAML スキーマコンテキストに似た XAML スキーマコンテキスト手法を使用します。

**Xamltype および Xamltype 拡張機能:** WPF は、プロパティの概念と、依存関係プロパティ、およびルーティングイベントによるイベントの概念を拡張します。 これらの概念を XAML 処理操作の可視性を高めるために、WPF は <xref:System.Xaml.XamlType> および <xref:System.Xaml.XamlMember> を拡張し、依存関係プロパティとルーティングイベント特性を報告する内部プロパティを追加します。

### <a name="accessing-the-wpf-xaml-schema-context"></a>WPF XAML スキーマコンテキストへのアクセス

WPF またはに基づく XAML 手法を使用している <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 場合 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType> 、wpf xaml スキーマコンテキストは、これらの xaml リーダーおよび xaml ライターの実装で既に使用されています。

WPF XAML スキーマコンテキストで初期化されない他の XAML リーダーまたは XAML ライターの実装を使用している場合は、の動作する WPF XAML スキーマコンテキストを取得できることがあり <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType> ます。 この値は、を使用する他の API の初期化として使用でき <xref:System.Xaml.XamlSchemaContext> ます。 たとえば、初期化のためにを呼び出し、 <xref:System.Xaml.XamlXmlReader.%23ctor%2A> WPF XAML スキーマコンテキストを渡すことができます。 または、XAML 型システム操作に WPF XAML スキーマコンテキストを使用することもできます。 これには、またはの構築の初期化、またはの呼び出しが含まれる場合があり <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType> ます。

純粋な XAML ノードストリームのパースペクティブから WPF XAML の特定の要素にアクセスする場合、WPF フレームワークの一部の機能がまだ使用されていない可能性があることに注意してください。 たとえば、コントロールの WPF テンプレートはまだ適用されていません。 したがって、実行時に完全なビジュアルツリーで設定されるプロパティにアクセスする場合、テンプレートを参照するプロパティ値のみが表示されることがあります。 WPF マークアップ拡張機能に対して提供されるサービスコンテキストは、非ランタイム状況から提供される場合には正確ではない場合もあり、オブジェクトグラフを書き込もうとすると例外が発生する可能性があります。

## <a name="xaml-and-assembly-loading"></a>XAML とアセンブリの読み込み

XAML および .NET XAML サービスのアセンブリの読み込みは、CLR によって定義されたの概念と統合され <xref:System.AppDomain> ます。 XAML スキーマコンテキストは、および他の要素の使用に基づいて、実行時またはデザイン時にアセンブリを読み込むか、型を検索する方法を解釈し <xref:System.AppDomain> ます。 このロジックは、xaml が xaml リーダーに対して厳密ではない xaml であるか、によって DLL にコンパイルされるか、 `XamlBuildTask` または WPF のによって BAML 生成されるかによって若干異なり `PresentationBuildTask` ます。

Wpf の XAML スキーマコンテキストは WPF アプリケーションモデルと統合されます。 wpf アプリケーションモデルは、wpf の <xref:System.AppDomain> 実装の詳細である他の要素と同様に使用されます。

#### <a name="xaml-reader-input-loose-xaml"></a>XAML リーダー入力 (ルース XAML)

01. XAML スキーマコンテキストは、アプリケーションのを反復処理し <xref:System.AppDomain> 、最後に読み込まれたアセンブリから開始して、名前のすべての側面に一致する、既に読み込まれているアセンブリを探します。 一致が見つかった場合は、そのアセンブリが解決に使用されます。

02. それ以外の場合は、CLR API に基づく次の方法のいずれかを使用して <xref:System.Reflection.Assembly> アセンブリを読み込みます。

    - 名前がマッピングで修飾されている場合は、 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 修飾名でを呼び出します。

    - 前の手順が失敗した場合は、短い名前 (および、存在する場合は公開キートークン) を使用してを呼び出し <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> ます。

    - マッピングで名前が修飾されていない場合は、を呼び出し <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> ます。

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask` は、Windows Communication Foundation (WCF) および Windows Workflow Foundation に使用されます。

を介したアセンブリ参照 `XamlBuildTask` は、常に完全修飾されていることに注意してください。

1. <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>修飾名でを呼び出します。

2. 前の手順が失敗した場合は、短い名前 (および、存在する場合は公開キートークン) を使用してを呼び出し <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> ます。

#### <a name="baml-presentationbuildtask"></a>BAML (プレゼンテーション Buildtask)

BAML のアセンブリの読み込みには2つの側面があります。 baml をコンポーネントとして含む初期アセンブリを読み込んで、BAML 運用によって参照される型の型バッキングアセンブリを読み込みます。

##### <a name="assembly-load-for-initial-markup"></a>初期マークアップのアセンブリの読み込み:

マークアップの読み込み元のアセンブリへの参照は、常に修飾されていません。

1. WPF XAML スキーマコンテキストは、WPF アプリケーションのを反復処理し <xref:System.AppDomain> 、最後に読み込まれたアセンブリから開始して、名前のすべての側面に一致する、既に読み込まれているアセンブリを探します。 一致が見つかった場合は、そのアセンブリが解決に使用されます。

2. 前の手順が失敗した場合は、短い名前 (および、存在する場合は公開キートークン) を使用してを呼び出し <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> ます。

##### <a name="assembly-references-by-baml-types"></a>BAML 型によるアセンブリ参照:

BAML 運用で使用される型のアセンブリ参照は、ビルドタスクの出力として常に完全修飾されます。

01. WPF XAML スキーマコンテキストは、WPF アプリケーションのを反復処理し <xref:System.AppDomain> 、最後に読み込まれたアセンブリから開始して、名前のすべての側面に一致する、既に読み込まれているアセンブリを探します。 一致が見つかった場合は、そのアセンブリが解決に使用されます。

02. それ以外の場合は、次の方法のいずれかを使用してアセンブリを読み込みます。

    - <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>修飾名でを呼び出します。
  
    - 短い名前と公開キートークンの組み合わせが、BAML が読み込まれたアセンブリと一致する場合は、そのアセンブリを使用します。

    - を呼び出すには、短い名前と公開キートークンを使用し <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> ます。

## <a name="see-also"></a>関連項目

- [XAML ノード ストリームの構造と概念について](understanding-xaml-node-stream-structures-and-concepts.md)
