---
title: x:FieldModifier ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3c27ffb6ba190c694926ea45a44ab4fb35564e90
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980149"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier ディレクティブ
名前付きオブジェクト参照のフィールドが既定の動作ではなくアクセスで定義されるように、XAML コンパイル動作を変更 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> します。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|*パブリック*|を指定するために渡す文字列は、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 使用される分離コードプログラミング言語によって異なります。 「解説」を参照してください。|

## <a name="dependencies"></a>依存関係

 XAML の運用環境で `x:FieldModifier` 任意の場所を使用する場合は、その xaml の運用環境のルート要素で [x:Class ディレクティブ](xclass-directive.md)を宣言する必要があります。

## <a name="remarks"></a>注釈

`x:FieldModifier` は、クラスまたはそのメンバーの一般アクセスレベルを宣言する場合には関係ありません。 Xaml の運用環境に含まれる特定の XAML オブジェクトが処理され、アプリケーションのオブジェクトグラフでアクセスできる可能性があるオブジェクトになる場合にのみ、XAML 処理の動作に関連します。 既定では、このようなオブジェクトのフィールド参照はプライベートに保持されるため、コントロールのコンシューマーがオブジェクトグラフを直接変更することはできません。 代わりに、コントロールコンシューマーは、レイアウトルート、子要素コレクション、専用のパブリックプロパティなどを取得することによって、プログラミングモデルによって有効になる標準パターンを使用して、オブジェクトグラフを変更する必要があります。

属性の値は `x:FieldModifier` プログラミング言語によって異なり、その目的は特定のフレームワークによって異なります。 使用する文字列は、各言語がを実装する方法、およびが返す型コンバーターによって異なり <xref:System.CodeDom.Compiler.CodeDomProvider> ます。これにより、との意味が定義され、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> その言語で大文字と小文字が区別されるかどうかが決まります。

- C# の場合、指定するために渡す文字列 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> は `public` です。

- Microsoft Visual Basic .NET の場合、指定するために渡す文字列 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> は `Public` です。

- C++/CLI では、XAML のターゲットは現在存在しません。したがって、渡す文字列は定義されていません。

(C# の場合は Visual Basic) を指定することもでき <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal` `Friend` ますが、 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `NotPublic` 動作が既に既定値であるため、を指定することは珍しくありません。

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> は、XAML をコンパイルしたアセンブリの外部のコードが XAML で作成された要素にアクセスする必要があるため、既定の動作です。 WPF のセキュリティアーキテクチャは、 `x:FieldModifier` パブリックアクセスを許可するように明示的に設定しない限り、XAML のコンパイル動作と共に、要素インスタンスをパブリックとして格納するフィールドを宣言しません。

`x:FieldModifier` は、public の後にフィールドを参照するために使用されるため、 [X:Name ディレクティブ](xname-directive.md) を持つ要素にのみ関連します。

既定では、ルート要素の部分クラスは public です。ただし、 [X:ClassModifier ディレクティブ](xclassmodifier-directive.md)を使用してパブリックにすることはできません。 [X:ClassModifier ディレクティブ](xclassmodifier-directive.md)は、ルート要素クラスのインスタンスのアクセスレベルにも影響します。 ルート要素にとの両方を含めることができます `x:Name` が、これによってルート要素のパブリックフィールドコピーが作成されるだけで `x:FieldModifier` 、 [x:ClassModifier ディレクティブ](xclassmodifier-directive.md)によって引き続き制御される true のルート要素クラスアクセスレベルが使用されます。

## <a name="see-also"></a>関連項目

- [WPF における XAML とカスタム クラス](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [WPF における分離コードと XAML](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name ディレクティブ](xname-directive.md)
- [WPF アプリケーションのビルド (WPF)](../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier ディレクティブ](xclassmodifier-directive.md)
