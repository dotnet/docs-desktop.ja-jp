---
title: x:Class ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: feada5fa118f3f39170a4d269155e71a56f5b085
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985408"
---
# <a name="xclass-directive"></a>x:Class ディレクティブ

マークアップと分離コードの間で部分クラスを結合するように、XAML マークアップのコンパイルを構成します。 コード部分クラスは、共通言語仕様 (CLS) 言語の個別のコードファイルで定義されます。一方、マークアップ部分クラスは、通常、XAML のコンパイル時にコード生成によって作成されます。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`namespace`|省略可能。 によって識別される部分クラスを含む CLR 名前空間を指定し `classname` ます。 を指定した場合 `namespace` 、ドット (.) は `namespace` とを分離し `classname` ます。 「解説」を参照してください。|
|`classname`|必須。 読み込まれた XAML とその XAML の分離コードを接続する部分クラスの CLR 名を指定します。|

## <a name="dependencies"></a>依存関係

`x:Class` は、XAML 運用環境のルート要素でのみ指定できます。 `x:Class` は、XAML 運用環境で親を持つオブジェクトでは無効です。 詳細については、「 [ \[ \] 4.3.1.6」セクション](/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。

## <a name="remarks"></a>注釈

値には、関連する名前 `namespace` 空間を名前階層に編成するための追加のドットが含まれている場合があります。これは、.net プログラミングにおける一般的な手法です。 値の文字列内の最後のドットのみ `x:Class` が分離され `namespace` 、 `classname.` として使用されるクラスは、入れ子になったクラスにする `x:Class` ことはできません。 入れ子になったクラスが許可されている場合、入れ子になったクラスは使用できません `x:Class` 。

を使用する既存のプログラミングモデルで `x:Class` `x:Class` は、分離コードのない XAML ページを持つことが完全に有効であるという意味では省略可能です。 ただし、この機能は、XAML を使用するフレームワークによって実装されるビルドアクションと対話します。 `x:Class` 機能は、XAML によって指定されたコンテンツのさまざまな分類がアプリケーションモデルとそれに対応するビルドアクションに存在するロールの影響も受けます。 XAML でイベント処理属性の値を宣言する場合、または定義するクラスが分離コードクラスに含まれるカスタム要素をインスタンス化する場合は、 `x:Class` コードビハインドの適切なクラスにディレクティブ参照 (または [x:Subclass](xsubclass-directive.md)) を指定する必要があります。

ディレクティブの値は、 `x:Class` クラスの完全修飾名を指定する文字列である必要があります。ただし、アセンブリ情報は含まれません (と同じ <xref:System.Type.FullName%2A?displayProperty=nameWithType> )。 単純なアプリケーションの場合、分離コードがその方法でも構造化されている場合は、CLR 名前空間の情報を省略できます (コード定義はクラスレベルで開始されます)。

ページまたはアプリケーション定義の分離コードファイルは、コンパイルされたアプリケーションを生成するプロジェクトの一部として含まれているコードファイル内に存在する必要があります。また、マークアップコンパイルも関係します。 CLR クラスの名前の規則に従う必要があります。 詳細については、「 [フレームワークのデザインガイドライン](/dotnet/api/)」を参照してください。 既定では、分離コードクラスはである必要がありますが、 `public` [x:ClassModifier ディレクティブ](xclassmodifier-directive.md)を使用して別のアクセスレベルで定義することもできます。

この属性の解釈は `x:Class` 、CLR ベースの xaml 実装 (特に .NET Xaml サービス) にのみ適用されます。 CLR に基づいていない、.NET XAML サービスを使用していない他の XAML 実装では、XAML マークアップの接続とランタイムコードのバックアップに別の解決式を使用する場合があります。 の一般的な解釈の詳細について `x:Class` は、「 [ \[ MS \] XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10))」を参照してください。

特定のレベルのアーキテクチャでは、の意味は `x:Class` .NET XAML サービスでは定義されていません。 これは、.NET XAML サービスでは、XAML マークアップとバッキングコードの接続に使用するプログラミングモデルが指定されていないためです。 ディレクティブのその他の使用方法は、 `x:Class` プログラミングモデルまたはアプリケーションモデルを使用して XAML マークアップと CLR ベースの分離コードを接続する方法を定義する特定のフレームワークによって実装される場合があります。 各フレームワークは独自のビルドアクションを持つことができ、ビルド環境に含まれる必要がある動作または特定のコンポーネントの一部を有効にすることができます。 フレームワーク内では、ビルドアクションは、分離コードに使用されている特定の CLR 言語によって異なる場合もあります。

## <a name="xclass-in-the-wpf-programming-model"></a>WPF プログラミングモデルにおける x:Class

WPF アプリケーションと WPF アプリケーションモデルでは、は、 `x:Class` xaml ファイルのルートであり、コンパイルされる (xaml がビルドアクションを持つ WPF アプリケーションプロジェクトに含まれる) 任意の要素の属性として、 `Page` または <xref:System.Windows.Application> コンパイル済みの wpf アプリケーションのアプリケーション定義のルートに対して、として宣言できます。 `x:Class`ページルートまたはアプリケーションルート以外の要素、またはコンパイルされていない WPF xaml ファイル上でを宣言すると、.NET Framework 3.0 および .NET Framework 3.5 WPF xaml コンパイラでコンパイル時エラーが発生します。 WPF での処理に関するその他の側面について `x:Class` は、「 [Wpf の分離コードと XAML](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)」を参照してください。

## <a name="xclass-for-windows-workflow-foundation"></a>Windows Workflow Foundation の x:Class

Windows Workflow Foundation の場合、は、 `x:Class` 全体が xaml で構成されるカスタムアクティビティのクラスに名前を付けます。または、分離コードを使用してアクティビティデザイナーの xaml ページの部分クラスに名前を付けます。

## <a name="silverlight-usage-notes"></a>Silverlight の使用上の注意

Silverlight 用の `x:Class` に関しては、別途ドキュメントが用意されています。 詳細については、「 [XAML 名前空間 (x:)」を参照してください。言語機能 (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))。

## <a name="see-also"></a>関連項目

- [x:Subclass ディレクティブ](xsubclass-directive.md)
- [WPF における XAML とカスタム クラス](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier ディレクティブ](xclassmodifier-directive.md)
- [WPF から App.xaml に移行された型](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
