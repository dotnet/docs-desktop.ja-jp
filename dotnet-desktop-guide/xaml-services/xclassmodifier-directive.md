---
title: x:ClassModifier ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 2d795ad1caa766d21ea98e5a97c98304067cbef1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980188"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier ディレクティブ

が指定されている場合に XAML のコンパイル動作 `x:Class` を変更します。 具体的には、アクセスレベル (既定値) を持つ部分を作成するのではなく、指定されたが `class` `Public` `x:Class` アクセスレベルで作成され `NotPublic` ます。 この動作は、生成されたアセンブリのクラスのアクセスレベルに影響します。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|*NotPublic*|を指定するために渡す正確な文字列は、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 使用する分離コードプログラミング言語によって異なります。 「解説」を参照してください。|

## <a name="dependencies"></a>依存関係

[x:Class](xclass-directive.md) も同じ要素に指定する必要があり、その要素はページのルート要素である必要があります。 詳細については、「 [ \[ \] 4.3.1.8」セクション](/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。

## <a name="remarks"></a>注釈

`x:ClassModifier`.NET XAML サービスの使用におけるの値は、プログラミング言語によって異なります。 使用する文字列は、各言語がを実装する方法、およびが返す型コンバーターによって異なり <xref:System.CodeDom.Compiler.CodeDomProvider> ます。これにより、との意味が定義され、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> その言語で大文字と小文字が区別されるかどうかが決まります。

- C# の場合、指定するために渡す文字列 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> は `internal` です。

- Microsoft Visual Basic .NET の場合、指定するために渡す文字列 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> は `Friend` です。

- C++/CLI では、XAML のコンパイルをサポートするターゲットは存在しません。したがって、渡す値は指定されていません。

を指定することもできます <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` C# の場合は `Public` Visual Basic)。ただし、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> は、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> が既に既定の動作であるため、を指定することはあまりありません。

C# のなど、ユーザーコードのアクセスレベルの制限が同じである他の値 `private` は、XAML では入れ子になったクラス参照がサポートされていないため、には関係ありません `x:ClassModifier` 。したがって、 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 修飾子は同じ効果を持ちます。

## <a name="security-notes"></a>セキュリティに関するメモ

で宣言されているアクセスレベル `x:ClassModifier` は、特定のフレームワークとその機能によって解釈されることもあります。 WPF には、の型を読み込んでインスタンス化する機能が含まれてい `x:ClassModifier` `internal` ます。これは、そのクラスが、パッケージ URI 参照を通じて WPF リソースから参照されている場合です。 このケースの結果として、他のフレームワークによって実装されている可能性がある場合は、を排他的に使用して、 `x:ClassModifier` 可能なすべてのインスタンス化試行をブロックしないでください。

## <a name="see-also"></a>関連項目

- [x:Class ディレクティブ](xclass-directive.md)
- [WPF における分離コードと XAML](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier ディレクティブ](xfieldmodifier-directive.md)
- [セキュリティ (WPF)](../framework/wpf/security-wpf.md)
- [WPF から App.xaml に移行された型](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
