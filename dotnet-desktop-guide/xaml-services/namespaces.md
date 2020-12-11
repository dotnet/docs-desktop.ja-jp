---
title: .NET XAML サービスの XAML 名前空間
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983452"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>.NET XAML サービスの XAML 名前空間
XAML 名前空間は、XML 名前空間の定義に基づいて拡張される概念です。 XML 名前空間と同様に、マークアップの属性を使用して XAML 名前空間を定義でき `xmlns` ます。 Xaml 名前空間は、xaml ノードストリームおよびその他の XAML サービス Api でも表されます。 このトピックでは、xaml 名前空間の概念を定義し、xaml 名前空間を定義する方法と、xaml スキーマコンテキストおよび .NET XAML サービスのその他の側面で xaml 名前空間を使用する方法について説明します。  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML 名前空間と XAML 名前空間  
 Xaml 名前空間は特殊な XML 名前空間であり、XAML は特殊な形式の XML であり、そのマークアップに基本的な XML 形式を使用します。 マークアップでは、 `xmlns` 要素に適用された属性を使用して、XAML 名前空間とそのマッピングを宣言します。 宣言は、 `xmlns` XAML 名前空間が宣言されているのと同じ要素に対して行うことができます。 要素に対して作成された XAML 名前空間の宣言は、その要素、その要素のすべての属性、およびその要素のすべての子に対して有効です。 属性では、属性を含む要素とは異なる XAML 名前空間を使用できます。ただし、属性名自体がマークアップで属性名の一部としてプレフィックスを参照している場合に限ります。  
  
 XAML 名前空間と XML 名前空間の違いは、XML 名前空間を使用してスキーマを参照したり、エンティティを区別したりすることです。 XAML では、XAML で使用される型とメンバーが最終的にはバッキング型に解決される必要があり、XML スキーマの概念はこの機能に適切に適用されません。 XAML 名前空間には、この型マッピングを実行するために XAML スキーマコンテキストが使用できる必要がある情報が含まれています。  
  
## <a name="xaml-namespace-components"></a>XAML 名前空間コンポーネント  
 XAML 名前空間の定義には、プレフィックスと識別子の2つのコンポーネントがあります。 これらの各コンポーネントは、XAML 名前空間がマークアップで宣言されている場合、または XAML 型システムで定義されている場合に存在します。  
  
 プレフィックスには、 [XML 1.0 仕様の W3C 名前空間](https://www.w3.org/TR/REC-xml-names/)で許可されている任意の文字列を指定できます。 慣例により、プレフィックスは一般的なマークアップファイルで何度も繰り返されるため、通常は短い文字列になります。 複数の XAML 実装で使用することを目的とした特定の XAML 名前空間では、特定の従来のプレフィックスが使用されます。 たとえば、XAML 言語の XAML 名前空間は、通常、プレフィックスを使用してマップされ `x` ます。 既定の XAML 名前空間を定義できます。ここでは、プレフィックスは定義で指定されていませんが、by.NET XAML サービス API を定義または照会した場合は空の文字列として表されます。 通常、XAML を実装するテクノロジとそのシナリオとボキャブラリによって、最大化されたプリフィックスの省略記号を昇格するために、既定の XAML 名前空間が意図的に選択されています。  
  
 識別子には、 [XML 1.0 仕様の W3C 名前空間](https://www.w3.org/TR/REC-xml-names/)で許可されている任意の文字列を指定できます。 慣例により、XML 名前空間または XAML 名前空間の識別子は、通常、URI 形式で指定されます。通常は、プロトコル修飾の絶対 URI です。 多くの場合、特定の XAML ボキャブラリを定義するバージョン情報は、パス文字列の一部として暗黙的に指定されます。 XAML 名前空間は、XML URI 規則を超えて、追加の識別子規則を追加します。 Xaml 名前空間の場合、識別子は、その XAML 名前空間の下で要素として指定された型を解決したり、属性をメンバーに解決したりするために、XAML スキーマコンテキストによって必要とされる情報を伝達します。  
  
 Xaml スキーマコンテキストに情報を伝達するために、XAML 名前空間の識別子は URI 形式である場合があります。 ただし、この場合、URI は特定のアセンブリまたはアセンブリのリスト内の一致する識別子としても宣言されます。 この処理は、アセンブリをで属性ことによって行い <xref:System.Windows.Markup.XmlnsDefinitionAttribute> ます。 XAML 名前空間を識別し、属性付きアセンブリで CLR ベースの型解決動作をサポートするこのメソッドは、.NET XAML サービスの既定の XAML スキーマコンテキストでサポートされています。 一般に、この規則は、XAML スキーマコンテキストに clr が組み込まれている場合、または clr アセンブリから CLR 属性を読み取るために必要な既定の XAML スキーマコンテキストに基づいている場合に使用できます。  
  
 XAML 名前空間は、CLR 名前空間と型定義アセンブリを通信する規則によって識別することもできます。 この規則は <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 、型を含むアセンブリに属性が存在しない場合に使用されます。 この規則は URI 規則よりも複雑になる可能性があります。また、アセンブリを参照する複数の方法があるため、あいまいさと重複が発生する可能性もあります。  
  
 CLR 名前空間とアセンブリ規約を使用する識別子の最も基本的な形式は次のとおりです。  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:` と `; assembly=` は、構文のリテラルコンポーネントです。  
  
 *Clrnsname* は、CLR 名前空間を識別する文字列名です。 この文字列名には、CLR 名前空間および他の CLR 名前空間との関係に関するヒントを提供する内部ドット文字 (.) が含まれます。
  
 *Assemblyshortname* は、XAML で有用な型を定義するアセンブリの文字列名です。 宣言された XAML 名前空間を介してアクセスされる型は、アセンブリによって定義され、 *Clrnsname* によって指定された CLR 名前空間内で宣言されることが想定されます。 この文字列名は、通常、によって報告された情報に似て <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> います。  
  
 CLR 名前空間とアセンブリ規則の完全な定義は次のとおりです。  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *assemblyName* は、入力として有効な任意の文字列を表し <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> ます。 この文字列には、カルチャ、公開キー、またはバージョン情報を含めることができます (これらの概念の定義はのリファレンストピックで定義されてい <xref:System.Reflection.Assembly> ます)。 COFF 形式と証拠 (の他のオーバーロードによって使用される <xref:System.Reflection.Assembly.Load%2A> ) は、XAML アセンブリの読み込みには関係ありません。すべての読み込み情報が文字列として表示される必要があります。  
  
 アセンブリの公開キーを指定することは、XAML セキュリティにとって便利な手法です。または、アセンブリが簡易名によって読み込まれる場合、またはキャッシュまたはアプリケーションドメインに事前に存在する場合に存在する可能性があるあいまいさを解消するために使用できます。 詳細については、「 [XAML のセキュリティに関する考慮事項](security-considerations.md)」を参照してください。  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Xaml サービス API での XAML 名前空間の宣言  
 XAML サービス API では、XAML 名前空間の宣言がオブジェクトによって表され <xref:System.Xaml.NamespaceDeclaration> ます。 コードで XAML 名前空間を宣言する場合は、コンストラクターを呼び出し <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> ます。 `ns`パラメーターと `prefix` パラメーターは文字列として指定され、これらのパラメーターに指定する入力は、このトピックで既に説明したように、xaml 名前空間識別子および xaml 名前空間プレフィックスの定義に対応します。  
  
 Xaml ノードストリームの一部として、または xaml 型システムへの他のアクセスを介して XAML 名前空間情報を調べる場合、は <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> xaml 名前空間識別子を報告し、 <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> xaml 名前空間プレフィックスを報告します。  
  
 Xaml ノードストリームでは、xaml 名前空間の情報は、適用先のエンティティの前に xaml ノードとして表示されます。 これには、xaml 名前空間の情報が XAML ルート要素のの前にある場合が含まれ `StartObject` ます。 詳細については、「 [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md)」を参照してください。  
  
 .NET XAML サービス API を使用する多くのシナリオでは、少なくとも1つの XAML 名前空間宣言が存在している必要があります。また、宣言には、XAML スキーマコンテキストで必要な情報を格納するか参照する必要があります。 XAML 名前空間は、読み込むアセンブリを指定するか、XAML スキーマコンテキストによって既に読み込まれているか既知のアセンブリ内の特定の型の解決を支援する必要があります。  
  
 Xaml ノードストリームを生成するには、xaml スキーマコンテキストを通じて xaml 型情報が使用可能である必要があります。 作成する各ノードに関連する XAML 名前空間を最初に決定しなければ、XAML 型情報を特定することはできません。 この時点では、型のインスタンスはまだ作成されていませんが、XAML スキーマコンテキストでは、定義するアセンブリとバッキング型から情報を検索する必要がある場合があります。 たとえば、マークアップを処理するには、 `<Party><PartyFavor/></Party>` xaml スキーマコンテキストでのの名前と型を決定できる必要があり `ContentProperty` `Party` ます。また、との xaml 名前空間の情報も把握している必要があり `Party` `PartyFavor` ます。 既定の XAML スキーマコンテキストの場合、静的なリフレクションは、ノードストリームで XAML 型ノードを生成するために必要な XAML 型システム情報の多くを報告します。  
  
 XAML ノードストリームからオブジェクトグラフを生成するには、元のマークアップで使用される xaml プレフィックスごとに xaml 名前空間宣言が存在し、XAML ノードストリームに記録される必要があります。 この時点で、インスタンスが作成され、実際の型マッピングの動作が発生します。  
  
 Xaml スキーマコンテキストで使用する xaml 名前空間がマークアップで定義されていない場合に、XAML 名前空間情報を事前に作成する必要がある場合、を使用する方法の1つとして、での XML 名前空間宣言の宣言があり <xref:System.Xml.XmlParserContext> <xref:System.Xml.XmlReader> ます。 次に <xref:System.Xml.XmlReader> 、XAML リーダーコンストラクターの入力として、またはを使用し <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType> ます。  
  
 .NET XAML サービスでの XAML 名前空間の処理に関連する他の2つの Api は、との属性です <xref:System.Windows.Markup.XmlnsDefinitionAttribute> <xref:System.Windows.Markup.XmlnsPrefixAttribute> 。 これらの属性は、アセンブリに適用されます。 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> は、URI を含むすべての XAML 名前空間宣言を解釈するために、XAML スキーマコンテキストによって使用されます。 <xref:System.Windows.Markup.XmlnsPrefixAttribute> は、XAML を生成するツールによって使用されます。これにより、特定の XAML 名前空間を予測可能なプレフィックスでシリアル化できるようになります。 詳細については、「 [カスタム型およびライブラリの XAML 関連の CLR 属性](clr-attributes-with-custom-types-and-libraries.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [XAML ノード ストリームの構造と概念について](understanding-xaml-node-stream-structures-and-concepts.md)
