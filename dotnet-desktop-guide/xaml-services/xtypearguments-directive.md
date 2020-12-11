---
title: x:TypeArguments ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985528"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments ディレクティブ

ジェネリックの制約型引数をジェネリック型のコンストラクターに渡します。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`object`|CLR ジェネリック型によってサポートされる XAML 型のオブジェクト要素宣言。 が `object` 既定の xaml 名前空間からではない xaml 型を参照している場合、は、が存在する場合に `object` xaml 名前空間を示すプレフィックスを必要とし `object` ます。|
|`typeString`|1つ以上の XAML 型名を文字列として宣言する文字列。この文字列は、CLR ジェネリック型の型引数を提供します。 追加の構文ノートについては、「解説」を参照してください。|

## <a name="remarks"></a>注釈

ほとんどの場合、文字列の情報項目として使用される XAML 型に `typeString` はプレフィックスが付きます。 Clr ジェネリック制約の一般的な型 (やなど <xref:System.Int32> ) は、 <xref:System.String> clr 基底クラスライブラリから取得されます。 これらのライブラリは、フレームワーク固有の一般的な既定の XAML 名前空間にマップされないため、XAML の使用にはプレフィックスマッピングが必要です。

複数の XAML 型名を指定するには、コンマ区切り記号を使用します。

ジェネリック制約自体がジェネリック型を使用する場合は、入れ子になった制約型の引数をかっこ () で囲むことができます。

この定義 `x:TypeArguments` は、.NET XAML サービスと CLR バッキングの使用に固有であることに注意してください。 言語レベルの定義については、 [ \[ \] 「5.3.11」セクション](/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。

## <a name="usage-examples"></a>使用例

これらの例では、次の XAML 名前空間定義が宣言されているものとします。

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>リスト\<String>

`<scg:List x:TypeArguments="sys:String" ...>`<xref:System.Collections.Generic.List%601>型引数を使用して新しいをインスタンス化 <xref:System.String> します。

### <a name="dictionarystringstring"></a>Dictionary\<String,String>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`<xref:System.Collections.Generic.Dictionary%602>2 つの型引数を使用して、新しいをインスタンス化 <xref:System.String> します。

### <a name="queuekeyvaluepairstringstring"></a>キュー<KeyValuePair\<String,String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`<xref:System.Collections.Generic.Queue%601> <xref:System.Collections.Generic.KeyValuePair%602> 内部制約型引数とを使用して、の制約を持つ新しいをインスタンス化し <xref:System.String> <xref:System.String> ます。

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 と WPF 汎用 XAML の使用

XAML 2006 の使用、および WPF アプリケーションで使用される XAML では、 `x:TypeArguments` 一般的に xaml からのジェネリック型の使用に関して次の制限があります。

- ジェネリック型を参照する汎用 XAML 使用をサポートできるのは、XAML ファイルのルート要素だけです。

- ルート要素は、少なくとも1つの型引数を持つジェネリック型にマップする必要があります。 たとえば <xref:System.Windows.Navigation.PageFunction%601> です。 ページ関数は、WPF の XAML 汎用使用サポートの主要なシナリオです。

- ジェネリックのルート要素 XAML オブジェクト要素も、を使用して部分クラスを宣言する必要があり `x:Class` ます。 これは、WPF ビルドアクションを定義する場合にも当てはまります。

- `x:TypeArguments` 入れ子になったジェネリック制約を参照することはできません。

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>WPF 3.0 または WPF 3.5 依存関係のない XAML 2009 または XAML 2006

XAML 2006 または XAML 2009 の .NET XAML サービスでは、ジェネリック XAML の使用に関する WPF 関連の制限が緩和されます。 バッキング型システムおよびオブジェクトモデルがサポートできる XAML マークアップ内の任意の位置で、ジェネリックオブジェクト要素をインスタンス化できます。

CLR 基本型をマップして共通言語プリミティブの XAML 型を取得するのではなく、XAML 2009 を使用する場合は、 [共通の Xaml 言語プリミティブの組み込み型](types-for-primitives.md) を内の情報項目として使用でき `typeString` ます。 たとえば、次のように宣言できます (プレフィックスの割り当ては表示されませんが、x は xaml 言語2009の xaml 言語の xaml 名前空間です)。

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

WPF で .NET Framework 4 または .NET Core 3.0 (またはそれ以降) を対象とする場合は、XAML 2009 の機能をと共に使用でき `x:TypeArguments` ますが、疎な xaml (マークアップコンパイルされていない xaml) に対してのみ使用できます。 WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。 XAML をマークアップする必要がある場合は、「 [xaml 2006 と WPF 汎用 xaml の使用](#xaml-2006-and-wpf-generic-xaml-usages) 」セクションに記載されている制限事項に従って操作する必要があります。 BAML は、.NET Framework でのみサポートされています。

## <a name="see-also"></a>関連項目

- [x:Class ディレクティブ](xclass-directive.md)
- [x:Type マークアップ拡張機能](xtype-markup-extension.md)
- [共通の XAML 言語プリミティブの組み込み型](types-for-primitives.md)
- [XAML のジェネリック](generics.md)
