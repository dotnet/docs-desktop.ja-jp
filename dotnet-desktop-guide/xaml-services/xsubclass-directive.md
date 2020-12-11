---
title: x:Subclass ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: 5da3634ac05b4f6a3825dae87e361003518b0830
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985736"
---
# <a name="xsubclass-directive"></a>x:Subclass ディレクティブ

が指定されている場合に XAML マークアップのコンパイル動作 `x:Class` を変更します。 に基づく部分クラスを作成する代わりに、 `x:Class` 指定されたが `x:Class` 中間クラスとして作成され、指定された派生クラスがに基づいていると想定され `x:Class` ます。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`namespace`|省略可能。 を含む CLR 名前空間を指定し `classname` ます。 を指定した場合 `namespace` 、ドット (.) は `namespace` とを分離し `classname` ます。|
|`classname`|必須。 読み込まれた XAML とその XAML の分離コードを接続する部分クラスの CLR 名を指定します。 「解説」を参照してください。|
|`subclassNamespace`|省略可能。 は `namespace` 、各名前空間が他の名前空間を解決できるかどうかとは異なる場合があります。 を含む CLR 名前空間を指定し `subclassName` ます。 を指定した場合 `subclassName` 、ドット (.) は `subclassNamespace` とを分離し `subclassName` ます。|
|`subclassName`|必須。 サブクラスの CLR 名を指定します。|

## <a name="dependencies"></a>依存関係

[X:Class ディレクティブ](xclass-directive.md) は、同じオブジェクトでも指定する必要があります。また、そのオブジェクトは XAML 運用のルート要素である必要があります。

## <a name="remarks"></a>注釈

`x:Subclass` 使用法は、主に部分クラス宣言をサポートしない言語を対象としています。

として使用されるクラスは、 `x:Subclass` 入れ子になったクラスにすることはできません。また、 `x:Subclass` 「依存関係」セクションで説明されているように、ルートオブジェクトを参照する必要があります。

それ以外の場合、の概念上の意味 `x:Subclass` は、.NET XAML サービスの実装によって定義されていません。 これは、.NET XAML サービスの動作では、XAML マークアップとバッキングコードの接続に使用されるプログラミングモデル全体が指定されていないためです。 およびに関連するその他の概念の実装 `x:Class` `x:Subclass` は、プログラミングモデルまたはアプリケーションモデルを使用して、XAML マークアップ、コンパイルされたマークアップ、および CLR ベースの分離コードを接続する方法を定義する特定のフレームワークによって実行されます。 各フレームワークには、動作の一部またはビルド環境に含まれる必要がある特定のコンポーネントを有効にする独自のビルドアクションがある場合があります。 フレームワーク内では、ビルドアクションは、分離コードに使用される特定の CLR 言語によって異なる場合もあります。

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

`x:Subclass` は、が既に存在するアプリケーション定義内のページルートまたはルートに配置でき <xref:System.Windows.Application> `x:Class` ます。 `x:Subclass`ページまたはアプリケーションルート以外の要素での宣言、または存在しない要素の指定により `x:Class` 、コンパイル時エラーが発生します。

このシナリオに対して正しく動作する派生クラスを作成するの `x:Subclass` は非常に複雑です。 場合によっては、中間ファイル (マークアップコンパイルによってプロジェクトの obj フォルダーに生成された g ファイル) を調べて、.xaml ファイル名が含まれている名前を使用する必要があります。 これらの中間ファイルを使用すると、コンパイルされたアプリケーションの部分クラスに結合されている特定のプログラミング構成要素の発生元を特定できます。

`internal override` `Friend Overrides` コンパイル時に中間クラスで作成されたハンドラーのスタブをオーバーライドするには、派生クラスのイベントハンドラーが (Microsoft Visual Basic) である必要があります。 それ以外の場合は、派生クラスの実装によって中間クラスの実装が非表示になり、中間クラスのハンドラーは呼び出されません。

との両方を定義する場合 `x:Class` `x:Subclass` 、によって参照されるクラスの実装を指定する必要はありません `x:Class` 。 属性を使用して名前を指定するだけで、 `x:Class` 中間ファイルに作成するクラスに関するガイダンスがコンパイラに提供されます (この場合、コンパイラは既定の名前を選択しません)。 クラスには実装を与えることができますが `x:Class` 、これはとの両方を使用する場合の一般的なシナリオではありません `x:Class` `x:Subclass` 。

## <a name="see-also"></a>関連項目

- [x:Class ディレクティブ](xclass-directive.md)
- [WPF における XAML とカスタム クラス](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
