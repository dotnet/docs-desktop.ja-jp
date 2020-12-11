---
title: カスタム型およびライブラリの XAML 関連の CLR 属性
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 509a4b638cf8df2974f1c08309faac25c2ba8c14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985760"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>カスタム型およびライブラリの XAML 関連の CLR 属性

このトピックでは、.NET XAML サービスによって定義される共通言語ランタイム (CLR) の属性について説明します。 また、.NET で定義されている他の CLR 属性についても説明します。この属性には、アプリケーションからアセンブリまたは型への XAML 関連のシナリオがあります。 これらの CLR 属性を持つ属性アセンブリ、型、またはメンバーは、型に関連する XAML 型システム情報を提供します。 Xaml ノードストリームを直接処理するために、または専用の XAML リーダーと XAML ライターを使用して、.NET XAML サービスを使用するすべての XAML コンシューマーに情報が提供されます。

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>カスタム型およびカスタムメンバーの CLR 属性の XAML-Related

CLR 属性を使用する場合は、CLR 全体を使用して型を定義する必要があります。そうしないと、このような属性は使用できません。 CLR を使用して型のバッキングを定義する場合、.NET XAML サービスの XAML ライターによって使用される既定の XAML スキーマコンテキストは、バッキングアセンブリに対するリフレクションを通じて CLR の属性を読み取ることができます。

以下のセクションでは、カスタム型またはカスタムメンバーに適用できる XAML 関連の属性について説明します。 各 CLR 属性は、XAML 型システムに関連する情報を伝達します。 読み込みパスでは、属性付き情報は、XAML リーダーが有効な XAML ノードストリームを形成するのに役立ちます。また、XAML ライターが有効なオブジェクトグラフを生成するのにも役立ちます。 保存パスでは、属性付きの情報により、xaml リーダーは xaml 型システム情報を再構成有効な XAML ノードストリームにすることができます。または、XAML ライターまたは他の XAML コンシューマーのシリアル化ヒントまたは要件を宣言します。

### <a name="ambientattribute"></a>AmbientAttribute

**リファレンスドキュメント:**<xref:System.Windows.Markup.AmbientAttribute>

**適用対象:** アタッチ可能なプロパティをサポートするクラス、プロパティ、または `get` アクセサーのメンバー。

**引数:** 存在

<xref:System.Windows.Markup.AmbientAttribute> プロパティ、または属性付きの型を受け取るすべてのプロパティを、XAML のアンビエントプロパティの概念で解釈する必要があることを示します。 アンビエントの概念は XAML プロセッサがメンバーの型の所有者を確認する方法と関連します。 アンビエントプロパティは、オブジェクトグラフを作成するときにパーサーコンテキストで値を使用できることが期待されるプロパティですが、すぐに作成される XAML ノードセットに対して一般的な型メンバーの参照は中断されます。

アンビエント概念はアタッチ可能なメンバーに適用できますが、CLR の属性で定義される方法の観点からはプロパティとしては表されません <xref:System.AttributeTargets> 。 メソッド属性の使用法は、 `get` XAML のアタッチ可能な使用をサポートするアクセサーに対してのみ適用する必要があります。

### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**適用対象:** 講義

**引数:** 単一のコンストラクター引数に一致するプロパティの名前を指定する文字列。

<xref:System.Windows.Markup.ConstructorArgumentAttribute> パラメーターなしのコンストラクター構文を使用してオブジェクトを初期化できること、および指定された名前のプロパティが構築情報を提供することを指定します。 この情報は主に XAML シリアル化用です。 詳細については、「<xref:System.Windows.Markup.ConstructorArgumentAttribute>」を参照してください。

### <a name="contentpropertyattribute"></a>ContentPropertyAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**適用対象:** 講義

**引数:** 属性付きの型のメンバーの名前を指定する文字列。

<xref:System.Windows.Markup.ContentPropertyAttribute> 引数によって指定されるプロパティが、その型の XAML コンテンツプロパティとして機能する必要があることを示します。 XAML コンテンツプロパティの定義は、定義する型に割り当てることができるすべての派生型に継承されます。 特定の派生型に対してを適用することで、特定の派生型の定義をオーバーライドでき <xref:System.Windows.Markup.ContentPropertyAttribute> ます。

XAML コンテンツプロパティとして機能するプロパティでは、プロパティのプロパティ要素のタグ付けを XAML の使用時に省略できます。 通常、コンテンツモデルとコンテインメントモデルの簡素化された XAML マークアップを促進する XAML コンテンツプロパティを指定します。 XAML コンテンツプロパティとして指定できるのは1つのメンバーだけなので、XAML コンテンツプロパティとして指定する必要がある型のいくつかのコンテナープロパティについて、設計上の選択肢がある場合があります。 その他のコンテナープロパティは、明示的なプロパティ要素と共に使用する必要があります。

XAML ノードストリームでは、XAML コンテンツプロパティは `StartMember` 、の `EndMember` プロパティの名前を使用して、およびノードを生成し <xref:System.Xaml.XamlMember> ます。 メンバーが XAML コンテンツプロパティであるかどうかを判断するには、 <xref:System.Xaml.XamlType> 位置から値を調べ、 `StartObject` の値を取得し <xref:System.Xaml.XamlType.ContentProperty%2A> ます。

### <a name="contentwrapperattribute"></a>ContentWrapperAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**適用対象:** クラス、特にコレクション型。

**引数:**<xref:System.Type>外部コンテンツのコンテンツラッパーの種類として使用する型を指定する。

<xref:System.Windows.Markup.ContentWrapperAttribute> 外部コンテンツをラップするために使用される、関連付けられたコレクション型の1つ以上の型を指定します。 外部コンテンツとは、コンテンツプロパティの型の型システム制約が、所有する型の XAML の使用によってサポートされる可能性のあるすべてのコンテンツケースをキャプチャしない場合を指します。 たとえば、特定の型のコンテンツに対する XAML サポートは、厳密に型指定されたジェネリックの文字列をサポートする場合があり <xref:System.Collections.ObjectModel.Collection%601> ます。 コンテンツラッパーは、既存のマークアップ規則を、テキスト関連のコンテンツモデルの移行など、コレクションの割り当て可能な値の XAML の構想に移行する場合に便利です。

複数のコンテンツラッパーの種類を指定するには、属性を複数回適用します。

### <a name="dependsonattribute"></a>依存関係の Sonattribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.DependsOnAttribute>

**適用対象:** "

**引数:** 属性付きの型の別のメンバーの名前を指定する文字列。

<xref:System.Windows.Markup.DependsOnAttribute> 属性付きプロパティが別のプロパティの値に依存していることを示します。 この属性をプロパティ定義に適用すると、XAML オブジェクトの書き込み時に依存プロパティが最初に処理されるようになります。 の使用法では <xref:System.Windows.Markup.DependsOnAttribute> 、特定の解析順序を有効なオブジェクト作成のために従う必要がある型のプロパティの例外的なケースを指定します。

複数 <xref:System.Windows.Markup.DependsOnAttribute> のケースをプロパティ定義に適用できます。

### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**適用対象:** クラス。派生型であることが想定されて <xref:System.Windows.Markup.MarkupExtension> います。

**引数:**<xref:System.Type> `ProvideValue` 属性付きの結果として予想される最も正確な型を指定する <xref:System.Windows.Markup.MarkupExtension> 。

詳細については、「 [XAML のマークアップ拡張機能の概要](markup-extensions-overview.md)」を参照してください。

### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**適用対象:** 講義

**引数:** は、次の2つの形式の属性をサポートします。

- 属性付きの型のプロパティの名前を指定する文字列。

- プロパティの名前、および <xref:System.Type> 名前付きプロパティを定義する型のを指定する文字列。 この形式は、アタッチ可能なメンバーを XAML 名前スコーププロパティとして指定するためのものです。

<xref:System.Windows.Markup.NameScopePropertyAttribute> 属性付きクラスの XAML 名前スコープの値を提供するプロパティを指定します。 XAML 名前スコーププロパティは、 <xref:System.Windows.Markup.INameScope> 実際の xaml 名前スコープ、ストア、およびその動作を実装して保持するオブジェクトを参照することが想定されています。

### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**適用対象:** 講義

**引数:** 属性付きの型の実行時の名前プロパティの名前を指定する文字列。

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> XAML [X:Name ディレクティブ](xname-directive.md)にマップされる属性付きの型のプロパティを報告します。 プロパティは型である必要があり、 <xref:System.String> 読み取り/書き込み可能である必要があります。

定義は、定義する型に割り当て可能なすべての派生型に継承されます。 特定の派生型に対してを適用することで、特定の派生型の定義をオーバーライドでき <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ます。

### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**適用対象:** な

**引数:** 存在.

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> は、空白の有意なコンテンツ (を持つコレクションによって保持されるコンテンツ) 内で子要素として表示される可能性のある特定の型に適用され <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> ます。 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> は、主に保存パスに関連しますが、を調べることによって、読み込みパスの XAML 型システムで使用でき <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType> ます。 詳細については、「 [XAML での空白の処理](white-space-processing.md)」を参照してください。

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**リファレンスドキュメント:**  <xref:System.ComponentModel.TypeConverterAttribute>

**適用対象:** クラス、プロパティ、メソッド (唯一の XAML 有効なメソッドケースは、 `get` アタッチ可能なメンバーをサポートするアクセサーです)。

**引数:**<xref:System.Type>の <xref:System.ComponentModel.TypeConverter> 。

<xref:System.ComponentModel.TypeConverterAttribute> XAML コンテキストでは、カスタムを参照し <xref:System.ComponentModel.TypeConverter> ます。 これ <xref:System.ComponentModel.TypeConverter> により、カスタム型の型変換動作、またはその型のメンバーが提供されます。

<xref:System.ComponentModel.TypeConverterAttribute>型コンバーターの実装を参照して、属性を型に適用します。 XAML の型コンバーターは、クラス、構造体、またはインターフェイスで定義できます。 列挙型の型変換を指定する必要はありません。変換はネイティブで有効になります。

型コンバーターは、マークアップ内の属性または初期化テキストに使用される文字列から目的の型に変換できる必要があります。 詳細については、「 [TypeConverters AND XAML](../framework/wpf/advanced/typeconverters-and-xaml.md)」を参照してください。

型のすべての値にを適用するのではなく、XAML の型コンバーターの動作を特定のプロパティに対して設定することもできます。 この場合は、 <xref:System.ComponentModel.TypeConverterAttribute> プロパティ定義 (特定のおよび定義ではなく、外側の定義) にを適用し `get` `set` ます。

カスタムアタッチ可能なメンバーの XAML 使用に対する型コンバーターの動作は、 <xref:System.ComponentModel.TypeConverterAttribute> `get` xaml の使用をサポートするメソッドアクセサーにを適用することによって割り当てることができます。

と同様に <xref:System.ComponentModel.TypeConverter> 、 <xref:System.ComponentModel.TypeConverterAttribute> XAML が存在する前に .net に存在し、型コンバーターモデルによって他の目的が提供されました。 を参照して使用するに <xref:System.ComponentModel.TypeConverterAttribute> は、を完全修飾するか、またはのステートメントを指定する必要があり `using` <xref:System.ComponentModel> ます。 また、プロジェクトにシステムアセンブリを含めます。

### <a name="uidpropertyattribute"></a>UidPropertyAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.UidPropertyAttribute>

**適用対象:** 講義

**引数:** 関連するプロパティを名前で参照する文字列。

[X:Uid ディレクティブ](xuid-directive.md)にエイリアスを指定するクラスの CLR プロパティを示します。

### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**適用対象:** 講義

**引数:** ブール値。 属性の目的で使用する場合は、値をに設定する必要があり `true` ます。

XAML オブジェクトグラフの作成中に、型が上から下に構築されるかどうかを示します。 これは高度な概念であり、プログラミングモデルの定義と密接に関連していると考えられます。 詳細については、「<xref:System.Windows.Markup.UsableDuringInitializationAttribute>」を参照してください。

### <a name="valueserializerattribute"></a>の属性

**リファレンスドキュメント:**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**適用対象:** クラス、プロパティ、メソッド (唯一の XAML 有効なメソッドケースは、 `get` アタッチ可能なメンバーをサポートするアクセサーです)。

**引数:**<xref:System.Type>属性付きの型のすべてのプロパティ、または特定の属性付きプロパティをシリアル化するときに使用する値シリアライザーサポートクラスを指定する。

<xref:System.Windows.Markup.ValueSerializer> よりも多くの状態とコンテキストを必要とする値シリアル化クラスを指定し <xref:System.ComponentModel.TypeConverter> ます。 <xref:System.Windows.Markup.ValueSerializer> アタッチ可能なメンバー <xref:System.Windows.Markup.ValueSerializerAttribute> の静的アクセサーメソッドに属性を適用することによって、アタッチできるメンバーに関連付けることができ `get` ます。 値のシリアル化は、列挙型、インターフェイス、および構造体にも適用できますが、デリゲートには適用できません。

### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**適用対象:** クラス。特に、混合コンテンツをホストすることが想定されているコレクション型。 UI 表現では、オブジェクト要素を囲む空白文字が重要になることがあります。

**引数:** 存在.

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> コレクション型を XAML プロセッサによって有意な空白として処理する必要があることを示します。これは、コレクション内の XAML ノードストリームの値ノードの構築に影響します。 詳細については、「 [XAML での空白の処理](white-space-processing.md)」を参照してください。

### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**適用対象:** クラス、プロパティ。

**引数:** は、文字列として、またはとして型として、2つの属性フォーム型をサポートし <xref:System.Type> ます 以下を参照してください。<xref:System.Windows.Markup.XamlDeferLoadAttribute>

クラスまたはプロパティに XAML の遅延読み込みの使用 (テンプレート動作など) が含まれていることを示し、遅延動作を有効にするクラスと、その宛先/コンテンツ タイプを報告します。

### <a name="xamlsetmarkupextensionattribute"></a>System.windows.markup.xamlsetmarkupextensionattribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**適用対象:** 講義

**引数:** コールバックに名前を付いています。

クラスがマークアップ拡張機能を使用して1つ以上のプロパティに値を提供できること、およびクラスの任意のプロパティに対してマークアップ拡張機能のセット操作を実行する前に XAML ライターが呼び出す必要があるハンドラーを参照することを示します。

### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**適用対象:** 講義

**引数:** コールバックに名前を付いています。

クラスが型コンバーターを使用して1つ以上のプロパティに値を提供できることを示します。また、クラスの任意のプロパティに対して型コンバーターの設定操作を実行する前に、XAML ライターが呼び出すハンドラーを参照します。

### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**適用対象:** 講義

**引数:** 属性付きの型に対してエイリアスを付けるプロパティの名前を指定する文字列 `xml:lang` 。

<xref:System.Windows.Markup.XmlLangPropertyAttribute> XML ディレクティブにマップされる属性付きの型のプロパティを報告し `lang` ます。 プロパティは必ずしも型であるとは限りません <xref:System.String> が、文字列から割り当て可能にする必要があります (代入は、型コンバーターをプロパティの型または特定のプロパティに関連付けることによって実現できます)。 プロパティは、読み取り/書き込み可能である必要があります。

マッピングのシナリオ `xml:lang` は、ランタイムオブジェクトモデルが、具体的には XMLDOM で処理することなく、XML で指定された言語情報にアクセスできるようにするためです。

定義は、定義する型に割り当て可能なすべての派生型に継承されます。 特定の派生型にを適用することで、特定の派生型の定義をオーバーライドできますが、これ <xref:System.Windows.Markup.XmlLangPropertyAttribute> は一般的なシナリオではありません。

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>アセンブリレベルでの CLR 属性の XAML-Related

以下のセクションでは、型またはメンバーの定義には適用されず、代わりにアセンブリに適用される XAML 関連の属性について説明します。 これらの属性は、XAML で使用するカスタム型を含むライブラリを定義する全体的な目標に関連します。 属性の一部は、必ずしも XAML ノードストリームに直接影響するわけではありませんが、他のコンシューマーが使用できるようにノードストリームで渡されます。 この情報のコンシューマーには、XAML 名前空間情報と関連するプレフィックス情報を必要とするデザイン環境またはシリアル化プロセスが含まれます。 XAML スキーマコンテキスト (.NET XAML サービスの既定値を含む) も、この情報を使用します。

### <a name="xmlnscompatiblewithattribute"></a>Xmlns/Withattribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**引数:**

- 適用する XAML 名前空間の識別子を指定する文字列。

- 前の引数から XAML 名前空間を適用できる XAML 名前空間の識別子を指定する文字列。

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> XAML 名前空間を別の XAML 名前空間で包括ことができることを指定します。 通常、包含する側の XAML 名前空間は、あらかじめ定義した <xref:System.Windows.Markup.XmlnsDefinitionAttribute> で示されます。 この手法を使用すると、ライブラリ内の XAML ボキャブラリのバージョンを管理し、以前にバージョン管理されたボキャブラリに対して以前に定義したマークアップと互換性を持たせることができます。

### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**引数:**

- 定義する XAML 名前空間の識別子を指定する文字列。

- CLR 名前空間に名前を指定する文字列。 CLR 名前空間はアセンブリでパブリック型を定義する必要があります。また、CLR 名前空間の型のうち少なくとも1つが XAML の使用を想定している必要があります。

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 名前空間と CLR 名前空間の間のアセンブリごとのマッピングを指定します。これは xaml オブジェクトライターまたは XAML スキーマコンテキストによる型の解決に使用されます。

  1つの <xref:System.Windows.Markup.XmlnsDefinitionAttribute> アセンブリに複数のを適用できます。 これは、次のいずれかの理由で実行される可能性があります。

- ライブラリの設計には、実行時 API アクセスの論理組織用に複数の CLR 名前空間が含まれています。ただし、同じ XAML 名前空間を参照することによって、これらの名前空間のすべての型を XAML で使用できるようにする必要があります。 この場合、 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 同じ値を使用して複数の属性を適用し <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> ますが、値は異なり <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> ます。 これは、フレームワークまたはアプリケーションが一般的な使用法で既定の XAML 名前空間として意図している XAML 名前空間のマッピングを定義する場合に特に便利です。

- ライブラリの設計には複数の CLR 名前空間が含まれており、これらの CLR 名前空間の型の使用について、意図的に XAML 名前空間を分離する必要があります。

- アセンブリに CLR 名前空間を定義し、複数の XAML 名前空間からアクセスできるようにします。 このシナリオは、同じコードベースを持つ複数のボキャブラリをサポートする場合に発生します。

- XAML 言語サポートは、1つまたは複数の CLR 名前空間で定義します。 この場合、値はになり <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> `http://schemas.microsoft.com/winfx/2006/xaml` ます。

### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute

**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**引数:**

- XAML 名前空間の識別子を指定する文字列。

- 推奨されるプレフィックスを指定する文字列。

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 名前空間に使用する推奨プレフィックスを指定します。 プレフィックスは、.NET XAML サービスによってシリアル化される XAML ファイルに要素や属性を書き込む場合や、xaml を <xref:System.Xaml.XamlXmlWriter> 実装するライブラリが xaml 編集機能を持つデザイン環境と対話する場合に便利です。

  1つの <xref:System.Windows.Markup.XmlnsPrefixAttribute> アセンブリに複数のを適用できます。 これは、次のいずれかの理由で実行される可能性があります。

- アセンブリでは、複数の XAML 名前空間の型が定義されています。 この場合は、XAML 名前空間ごとに異なるプレフィックス値を定義します。

- 複数のボキャブラリをサポートし、各ボキャブラリと XAML 名前空間に異なるプレフィックスを使用します。

- アセンブリに XAML 言語サポートを定義し、にを設定し <xref:System.Windows.Markup.XmlnsDefinitionAttribute> `http://schemas.microsoft.com/winfx/2006/xaml` ます。 この場合は、通常、プレフィックスを昇格させる必要があり `x` ます。

> [!NOTE]
> .NET XAML サービスでは、XAML 関連の属性も定義 <xref:System.Windows.Markup.RootNamespaceAttribute> します。 この属性は、プロジェクトシステムサポートのアセンブリレベルの属性であり、XAML カスタム型には関連しません。

## <a name="see-also"></a>関連項目

- <xref:System.Attribute>
- [.NET XAML サービスで使用するカスタム型の定義](define-custom-types.md)
