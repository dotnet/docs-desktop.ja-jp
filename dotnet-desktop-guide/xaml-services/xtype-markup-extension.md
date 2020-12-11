---
title: x:Type マークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: dae1fe820b2baa32b5519b6ac8c9b103baded300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982023"
---
# <a name="xtype-markup-extension"></a>x:Type マークアップ拡張機能

<xref:System.Type>指定された XAML 型の基になる型である CLR オブジェクトを提供します。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>XAML オブジェクト要素の使用方法

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`prefix`|省略可能。 既定以外の XAML 名前空間をマップするプレフィックス。 多くの場合、プレフィックスを指定する必要はありません。 「解説」を参照してください。|
|`typeNameValue`|必須。 現在の既定の XAML 名前空間に解決可能な型名。または、が指定されている場合は、指定されたマップされたプレフィックス `prefix` 。|

## <a name="remarks"></a>注釈

`x:Type`マークアップ拡張機能には、 `typeof()` C# の演算子または Microsoft Visual Basic の演算子と同様の関数があり `GetType` ます。

`x:Type`マークアップ拡張機能は、型を受け取るプロパティに対して、文字列変換動作を提供し <xref:System.Type> ます。 入力は XAML 型です。 入力 XAML 型と出力 CLR の関係では、 <xref:System.Type> <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlType> xaml スキーマコンテキストとコンテキストによって提供されるサービスに基づいて必要なを検索した後、出力は入力のになり <xref:System.Windows.Markup.IXamlTypeResolver> ます。

.NET XAML サービスでは、このマークアップ拡張機能の処理はクラスによって定義され <xref:System.Windows.Markup.TypeExtension> ます。

特定のフレームワーク実装では、 <xref:System.Type> 値として使用される一部のプロパティは、型の名前 (型の文字列値) を直接受け入れることができ `Name` ます。 ただし、この動作の実装は複雑なシナリオです。 例については、後述の「WPF の使用に関する注意事項」を参照してください。

属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。 `x:Type` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 拡張クラスの <xref:System.Windows.Markup.TypeExtension> 値として割り当てられます。 CLR 型に基づく .NET XAML サービスの既定の XAML スキーマコンテキストでは、この属性の値は <xref:System.Reflection.MemberInfo.Name%2A> 目的の型の、またはその <xref:System.Reflection.MemberInfo.Name%2A> 前に既定以外の xaml 名前空間マッピングのプレフィックスが付いているを含んでいます。

`x:Type`マークアップ拡張機能は、オブジェクト要素構文で使用できます。 この場合、 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 拡張機能を正しく初期化するには、プロパティの値を指定する必要があります。

`x:Type`マークアップ拡張機能は、verbose 属性としても使用できます。ただし、この使用は一般的ではありません。`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

### <a name="default-xaml-namespace-and-type-mapping"></a>既定の XAML 名前空間と型のマッピング

WPF プログラミングの既定の XAML 名前空間には、一般的な XAML シナリオに必要な XAML 型の大部分が含まれています。そのため、多くの場合、XAML 型の値を参照するときにプレフィックスを避けることができます。 カスタムアセンブリの型を参照している場合、または WPF アセンブリに存在するが、既定の XAML 名前空間にマップされていない CLR 名前空間の型を参照している場合は、プレフィックスの割り当てが必要になることがあります。 プレフィックス、XAML 名前空間、および CLR 名前空間のマッピングの詳細については、「 [WPF xaml の Xaml 名前空間と名前空間のマッピング](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)」を参照してください。

### <a name="type-properties-that-support-typename-as-string"></a>文字列型としての Typename をサポートする型プロパティ

WPF は <xref:System.Type> 、 `x:Type` マークアップ拡張機能の使用を必要とせずに、型の一部のプロパティの値を指定できるようにする手法をサポートしています。 代わりに、型に名前を付けた文字列として値を指定できます。 この例 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> として、とが <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType> あります。 この動作のサポートは、型コンバーターまたはマークアップ拡張機能では提供されません。 代わりに、これはを介して実装される遅延動作です <xref:System.Windows.FrameworkElementFactory> 。

Silverlight は同様の規則をサポートしています。 実際、Silverlight は、XAML 言語サポートでは現在サポートされておらず、 `{x:Type}` `{x:Type}` WPF-Silverlight xaml 移行をサポートするように設計されたいくつかの状況以外では使用できません。 そのため、typename としての typename の動作は、が値であるすべての Silverlight ネイティブプロパティ評価に組み込まれてい <xref:System.Type> ます。

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 は、ジェネリック型の追加サポートを提供し、 `x:TypeArguments` `x:Type` このサポートを提供するためにおよびの機能の動作を変更します。

- `x:TypeArguments` また、ジェネリックオブジェクトのインスタンス化に関連付けられたオブジェクト要素は、ルート以外の要素にもできます。 詳細については、 [X:TypeArguments ディレクティブ](xtypearguments-directive.md)の「XAML 2009」セクションを参照してください。

- XAML 2009 では、マークアップでジェネリック型の制約を指定するための構文がサポートされています。 これは `x:TypeArguments` 、、、 `x:Type` またはの2つの機能の組み合わせによって使用できます。

- XAML 2009 を読み込み用に処理するときの WPF XAML の実装では、型を使用する特定のフレームワークプロパティの暗黙的な型変換動作にもこの機能が追加され <xref:System.Type> ます。

WPF では、XAML 2009 の機能を使用できますが、ルース XAML (マークアップコンパイルされていない XAML) に対してのみ使用できます。 WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Style>
- [スタイルとテンプレート](../net/wpf/fundamentals/styles-templates-overview.md)
- [XAML の概要 (WPF)](../net/wpf/fundamentals/xaml.md)
- [マークアップ拡張機能と WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
