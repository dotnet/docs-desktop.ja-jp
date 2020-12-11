---
title: .NET XAML サービスで使用するカスタム型の定義
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: 2af59edfac430a1804cff3ffb0ab34df6b550f0a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985755"
---
# <a name="define-custom-types-for-use-with-net-xaml-services"></a>.NET XAML サービスで使用するカスタム型の定義

ビジネスオブジェクトまたは特定のフレームワークに依存しない型のカスタム型を定義する場合は、XAML のベストプラクティスに従うことができます。 これらの方法に従うと、.NET XAML サービスとその XAML リーダーおよび XAML ライターは、型の XAML 特性を検出し、xaml 型システムを使用して XAML ノードストリームに適切な表現を与えることができます。 このトピックでは、型定義、メンバー定義、および型またはメンバーの CLR 属性のベストプラクティスについて説明します。

## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>XAML のコンストラクターパターンと型定義

XAML でオブジェクト要素としてインスタンス化するには、カスタムクラスが次の要件を満たしている必要があります。

- カスタムクラスはパブリックである必要があり、パラメーターなしのパブリックコンストラクターを公開する必要があります。 (構造に関する注意事項については、次のセクションを参照してください)。

- カスタムクラスを入れ子にすることはできません。 フルネームパスの余分な "ドット" により、クラス名前空間の除算があいまいになり、添付プロパティなどの他の XAML 機能と干渉します。
オブジェクトをオブジェクト要素としてインスタンス化できる場合、作成されたオブジェクトは、基になる型としてオブジェクトを受け取るプロパティのプロパティ要素の形式を満たすことができます。

値コンバーターを有効にした場合でも、これらの条件を満たしていない型のオブジェクト値を提供できます。 詳細については、「 [XAML の型コンバーターとマークアップ拡張機能](type-converters-and-markup-extensions.md)」を参照してください。

### <a name="structures"></a>構造体

構造体は、常に CLR 定義によって XAML で構築できます。 これは、CLR コンパイラが構造体のパラメーターなしのコンストラクターを暗黙的に作成するためです。 このコンストラクターは、すべてのプロパティ値を既定値に初期化します。

場合によっては、構造体の既定の構築動作は望ましくありません。 これは、構造体が値を入力し、概念的に共用体として機能することを意図しているためです。 共用体として、含まれる値は相互に排他的な解釈を持つ場合があります。したがって、プロパティは設定できません。 WPF のボキャブラリにおけるこのような構造の例としては、が <xref:System.Windows.GridLength> あります。 このような構造体では、構造体の値の異なる解釈やモードを作成する文字列規則を使用して、値を属性形式で表現できるように、型コンバーターを実装する必要があります。 また、構造体では、パラメーターありのコンストラクターを使用してコードを構築するための同様の動作も公開する必要があります。

### <a name="interfaces"></a>インターフェイス

インターフェイスは、メンバーの基になる型として使用できます。 XAML 型システムは、割り当て可能なリストを確認し、値として指定されたオブジェクトをインターフェイスに割り当てることができることを前提としています。 関連する割り当て可能な型が XAML 構築の要件をサポートしている限り、インターフェイスを XAML 型として提示する方法の概念はありません。

### <a name="factory-methods"></a>ファクトリメソッド

ファクトリメソッドは XAML 2009 機能です。 これらは、オブジェクトにパラメーターなしのコンストラクターが必要であることを XAML 原則を変更します。 ファクトリメソッドについては、この記事では説明しません。 「 [X:FactoryMethod ディレクティブ](xfactorymethod-directive.md)」を参照してください。

## <a name="enumerations"></a>列挙型

列挙には、XAML ネイティブ型の変換動作があります。 XAML で指定された列挙定数名は、基になる列挙型に対して解決され、その列挙値を XAML オブジェクトライターに返します。

XAML は、適用された列挙に対するフラグ形式の使用をサポート <xref:System.FlagsAttribute> します。 詳細については、「 [XAML 構文の詳細](../framework/wpf/advanced/xaml-syntax-in-detail.md)」を参照してください。 ([Xaml 構文の詳細に](../framework/wpf/advanced/xaml-syntax-in-detail.md) ついては、WPF の対象ユーザー向けに記述されていますが、そのトピックのほとんどの情報は、特定の実装フレームワークに固有ではない xaml に関連しています)。

## <a name="member-definitions"></a>メンバーの定義

型は、XAML の使用のためにメンバーを定義できます。 特定の型が XAML で使用できない場合でも、型で XAML に使用できるメンバーを定義できます。 これは、CLR 継承が原因で発生する可能性があります。 メンバーを継承する型が XAML の使用を型としてサポートしていて、そのメンバーが基になる型の XAML の使用をサポートしている場合、またはネイティブ XAML 構文を使用できる場合、そのメンバーは XAML で使用できます。

### <a name="properties"></a>Properties

一般的な CLR およびアクセサーパターンと言語に適したキー表現を使用してプロパティをパブリック CLR プロパティとして定義すると、 `get` `set` XAML 型システムは、プロパティを、やなどのプロパティに対して提供される適切な情報と共にメンバーとして報告でき <xref:System.Xaml.XamlMember> <xref:System.Xaml.XamlMember.IsReadPublic%2A> <xref:System.Xaml.XamlMember.IsWritePublic%2A> ます。

特定のプロパティを適用することによって、テキスト構文を有効にすることができ <xref:System.ComponentModel.TypeConverterAttribute> ます。 詳細については、「 [XAML の型コンバーターとマークアップ拡張機能](type-converters-and-markup-extensions.md)」を参照してください。

テキスト構文またはネイティブ XAML 変換が存在しない場合、また、マークアップ拡張機能の使用など、追加の間接参照が存在しない場合、( <xref:System.Xaml.XamlMember.TargetType%2A> xaml 型システム内の) プロパティの型は、対象の型を CLR 型として扱うことによって、インスタンスを xaml オブジェクトライターに返すことができる必要があります。

XAML 2009 を使用している場合、前の考慮事項が満たされていない場合、 [X:Reference マークアップ拡張機能](xreference-markup-extension.md) を使用して値を指定できます。ただし、これは、型定義の問題よりも使用の問題になります。

### <a name="events"></a>イベント

イベントをパブリック CLR イベントとして定義すると、XAML 型システムはとしてのメンバーとしてイベントを報告でき <xref:System.Xaml.XamlMember.IsEvent%2A> `true` ます。 イベントハンドラーの配線は、.NET XAML サービスの機能の範囲内ではありません。配線は、特定のフレームワークと実装に残されます。

### <a name="methods"></a>メソッド

メソッドのインラインコードは、既定の XAML 機能ではありません。 ほとんどの場合、XAML からメソッドメンバーを直接参照するのではなく、XAML のメソッドのロールは特定の XAML パターンのサポートのみを提供します。 [X:FactoryMethod ディレクティブ](xfactorymethod-directive.md) は例外です。

### <a name="fields"></a>フィールド

CLR デザインガイドラインでは、非静的フィールドを防ぐことができます。 静的フィールドの場合は、 [X:Static マークアップ拡張機能](xstatic-markup-extension.md)を使用してのみ、静的フィールド値にアクセスできます。この場合は、CLR 定義で特別な処理を行わずに、 [x:Static](xstatic-markup-extension.md) usage のフィールドを公開しています。

## <a name="attachable-members"></a>アタッチ可能なメンバー

アタッチ可能なメンバーは、定義する型のアクセサーメソッドパターンを通じて XAML に公開されます。 定義する型自体は、オブジェクトとして XAML で使用できる必要はありません。 実際、一般的なパターンは、アタッチ可能なメンバーを所有し、関連する動作を実装する役割を持つサービスクラスを宣言することですが、UI 表現などの他の機能は提供しません。 次のセクションでは、プレースホルダー *PropertyName* はアタッチ可能なメンバーの名前を表しています。 この名前は、 [XamlName 文法](xamlname-grammar.md)で有効である必要があります。

これらのパターンと型の他のメソッドとの間で名前の競合が発生している場合は注意してください。 いずれかのパターンに一致するメンバーが存在する場合、そのメンバーは、意図していない場合でも、XAML プロセッサによってアタッチ可能なメンバーの使用経路として解釈されます。

#### <a name="the-getpropertyname-accessor"></a>GetPropertyName アクセサー

アクセサーのシグネチャは `GetPropertyName` 次のようにする必要があります。

`public static object GetPropertyName(object target)`

- `target` オブジェクトは、実装のより具体的な型として指定することができます。 これを使用して、アタッチ可能なメンバーの使用をスコープすることができます。意図したスコープ外の使用法は、XAML 解析エラーによって表示される無効なキャスト例外をスローします。 パラメーター名は `target` 要件ではありませんが、 `target` ほとんどの実装では規約によって名前が付けられます。

- 戻り値は、実装のより具体的な型として指定することができます。

<xref:System.ComponentModel.TypeConverter>アタッチ可能なメンバーの属性使用に対して有効なテキスト構文をサポートするには、 <xref:System.ComponentModel.TypeConverterAttribute> アクセサーにを適用し `GetPropertyName` ます。 の代わりにを適用すると、 `get` `set` 直観的に見えないように思えるかもしれませんが、この規則では、シリアル化できる読み取り専用のアタッチ可能なメンバーの概念をサポートできます。これは、デザイナーのシナリオで役に立ちます。

#### <a name="the-setpropertyname-accessor"></a>SetPropertyName アクセサー

アクセサーのシグネチャは `SetPropertyName` 次のようにする必要があります。

`public static void SetPropertyName(object target, object value)`

- オブジェクトは、 `target` 前のセクションで説明したのと同じロジックと結果を使用して、実装でより具体的な型として指定できます。

- `value` オブジェクトは、実装のより具体的な型として指定することができます。

このメソッドの値は、XAML の使用 (通常は属性の形式) からの入力であることに注意してください。 属性形式では、テキスト構文に対して値コンバーターがサポートされている必要があります。また、s アクセサーに属性を設定する必要があり `GetPropertyName` ます。

### <a name="attachable-member-stores"></a>アタッチ可能なメンバーストア

アクセサーメソッドは、通常、アタッチ可能なメンバー値をオブジェクトグラフに配置したり、オブジェクトグラフから値を取得して適切にシリアル化したりするための手段を提供するためのものではありません。 この機能を提供するには、 `target` 前のアクセサーシグネチャのオブジェクトが値を格納できる必要があります。 ストレージメカニズムは、アタッチ可能なメンバーがメンバーリストに含まれていないターゲットにアタッチできるメンバーである、アタッチ可能なメンバープリンシパルと一致している必要があります。 .NET XAML サービスは、Api およびを通じて、アタッチ可能なメンバーストアの実装手法を提供し <xref:System.Xaml.IAttachedPropertyStore> <xref:System.Xaml.AttachablePropertyServices> ます。 <xref:System.Xaml.IAttachedPropertyStore> は、XAML ライターがストアの実装を検出するために使用し、アクセサーのである型に実装する必要があり `target` ます。 静的 api は、 <xref:System.Xaml.AttachablePropertyServices> アクセサーの本体内で使用され、によってアタッチ可能なメンバーを参照し <xref:System.Xaml.AttachableMemberIdentifier> ます。

## <a name="xaml-related-clr-attributes"></a>CLR 属性の XAML-Related

XAML 型システム情報を .NET XAML サービスに報告するには、型、メンバー、およびアセンブリを正しく属性することが重要です。 XAML 型システム情報の報告は、次のいずれかの状況に該当する場合に関連します。

- .NET XAML サービスの XAML リーダーと XAML ライターに直接基づいている XAML システムで、型を使用します。
- Xaml を利用するフレームワークは、xaml リーダーと XAML ライターに基づいて定義または使用します。

カスタム型の XAML サポートに関連する各 XAML 関連の属性の一覧については、「 [カスタム型およびライブラリの Xaml 関連の CLR 属性](clr-attributes-with-custom-types-and-libraries.md)」を参照してください。

## <a name="usage"></a>使用方法

カスタム型を使用するには、マークアップの作成者が、カスタム型を含むアセンブリと CLR 名前空間のプレフィックスをマップする必要があります。 この手順については、このトピックでは説明しません。

## <a name="access-level"></a>アクセス レベル

XAML には、アクセスレベルを持つ型を読み込んでインスタンス化するための手段が用意されて `internal` います。 この機能は、ユーザーコードが独自の型を定義し、同じユーザーコードスコープの一部でもあるマークアップからそれらのクラスをインスタンス化できるようにするために用意されています。

WPF の例として、ユーザーコードでは、UI 動作をリファクターする方法として使用するを定義して <xref:System.Windows.Controls.UserControl> いますが、サポートクラスをアクセスレベルで宣言することによって暗黙的に考えられる可能性のある拡張機能の一部としては使用しない場合があり `public` ます。 <xref:System.Windows.Controls.UserControl> `internal` バッキングコードが XAML 型として参照される同じアセンブリにコンパイルされる場合、そのようなをアクセスで宣言できます。

完全信頼で XAML を読み込んで使用するアプリケーションの場合 <xref:System.Xaml.XamlObjectWriter> 、アクセスレベルを持つクラスの読み込み `internal` は常に有効になります。

部分信頼で XAML を読み込むアプリケーションの場合は、API を使用してアクセスレベルの特性を制御でき <xref:System.Xaml.Permissions.XamlAccessLevel> ます。 また、遅延メカニズム (WPF テンプレートシステムなど) は、すべてのアクセスレベルのアクセス許可を伝達し、最終的な実行時の評価のためにそれらを保持できる必要があります。これは、情報を渡すことによって内部的に処理され <xref:System.Xaml.Permissions.XamlAccessLevel> ます。

### <a name="wpf-implementation"></a>WPF の実装

WPF XAML では、部分信頼アクセスモデルが使用されます。この場合、BAML が部分信頼で読み込まれると、 <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> baml ソースであるアセンブリに対するアクセスはに制限されます。 遅延の場合、WPF は <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> アクセスレベル情報を渡すメカニズムとしてを使用します。

WPF XAML 用語では、 *内部型* は、参照元の xaml も含む同じアセンブリによって定義される型です。 このような型は、などのように、アセンブリを意図的に除外する XAML 名前空間を使用してマップでき `xmlns:local="clr-namespace:WPFApplication1"` ます。 BAML が内部型を参照し、その型にアクセスレベルがある場合 `internal` 、 `GeneratedInternalTypeHelper` アセンブリのクラスが生成されます。 回避する必要がある場合 `GeneratedInternalTypeHelper` は、アクセスレベルを使用するか、 `public` 関連するクラスを別のアセンブリにファクタリングして、そのアセンブリを依存させる必要があります。

## <a name="see-also"></a>関連項目

- [カスタム型およびライブラリの XAML 関連の CLR 属性](clr-attributes-with-custom-types-and-libraries.md)
- [XAML サービス](/dotnet/api/)
