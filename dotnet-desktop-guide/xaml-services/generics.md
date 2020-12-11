---
title: XAML のジェネリック
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985747"
---
# <a name="generics-in-xaml"></a>XAML のジェネリック

に実装されている .NET XAML サービスで <xref:System.Xaml?displayProperty=fullName> は、ジェネリック CLR 型の使用がサポートされています。 このサポートには、ジェネリックの制約を型引数として指定し、 `Add` ジェネリックコレクションケースに対して適切なメソッドを呼び出すことによって制約を適用する機能が含まれます。 このトピックでは、XAML でのジェネリック型の使用と参照の側面について説明します。

## <a name="xtypearguments"></a>x:TypeArguments

`x:TypeArguments` は、XAML 言語で定義されたディレクティブです。 ジェネリック型によってサポートされる XAML 型のメンバーとして使用されている場合、は、 `x:TypeArguments` ジェネリックの制約型引数をバッキングコンストラクターに渡します。 .NET XAML サービスに関連する参照構文の例については、 `x:TypeArguments` 「 [x:TypeArguments ディレクティブ](xtypearguments-directive.md)」を参照してください。

は文字列を受け取り、型コンバーターを使用しているため `x:TypeArguments` 、通常は属性として XAML の使用法で宣言されます。

XAML ノードストリームでは、によって宣言された情報は、 `x:TypeArguments` <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> `StartObject` ノードストリーム内の位置から取得できます。 の戻り値 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> は、値のリストです <xref:System.Xaml.XamlType> 。 XAML 型がジェネリック型を表すかどうかの判断は、を呼び出すことによって行うことができ <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType> ます。

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>XAML のジェネリックの規則と構文規則

XAML では、ジェネリック型は常に制約付きジェネリックとして表す必要があります。 制約のないジェネリックは、XAML 型システムまたは XAML ノードストリームには存在せず、XAML マークアップでは表現できません。 ジェネリックは、によって参照されているジェネリックの入れ子にされた型制約である場合 `x:TypeArguments` 、またはが `x:Type` ジェネリック型の CLR 型参照を提供する場合に、XAML 属性構文内で参照できます。 ジェネリックの参照は、 <xref:System.Xaml.Schema.XamlTypeTypeConverter> .NET XAML サービスによって定義されたクラスによってサポートされます。

によって有効にされる XAML 属性構文形式では、 <xref:System.Xaml.Schema.XamlTypeTypeConverter> ジェネリックの型や制約に山かっこを使用する一般的な MSIL/CLR 構文規則が変更され、代わりに制約コンテナーに対してかっこが代わりに使用されます。 例については、「 [X:TypeArguments ディレクティブ](xtypearguments-directive.md)」を参照してください。

## <a name="generics-and-xaml-2009-features"></a>ジェネリックおよび XAML 2009 の機能

CLR 基本型をマップして共通言語プリミティブの XAML 型を取得するのではなく、XAML 2009 を使用する場合は、の情報項目として [xaml 2009 組み込み型](types-for-primitives.md) を使用でき `x:TypeArguments` ます。 たとえば、次のように宣言することができます (このプレフィックスは表示されませんが、xaml `x` 言語の xaml 名前空間は xaml 2009)。

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>WPF でのジェネリックのサポート

WPF を特に対象とする XAML 2006 の使用については、 [x:Class](xclass-directive.md) もと同じ要素に指定する必要があり、 `x:TypeArguments` その要素は xaml ドキュメントのルート要素である必要があります。 ルート要素は、少なくとも1つの型引数を持つジェネリック型にマップする必要があります。 たとえば <xref:System.Windows.Navigation.PageFunction%601> です。

一般的な使用法をサポートするための回避策として、ジェネリック型を返すことができるカスタムマークアップ拡張機能の定義や、ジェネリック型から派生し、独自のクラス定義でジェネリック制約を平坦化するラップクラス定義の指定などがあります。

WPF では、XAML 2009 の機能をと共に使用でき `x:TypeArguments` ますが、ルース xaml (マークアップコンパイルされていない xaml) に対してのみ使用できます。 WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。

.NET Framework 3.5 の Windows Workflow Foundation のカスタムワークフローでは、一般的な XAML 使用はサポートされていません。

## <a name="see-also"></a>関連項目

- [x:TypeArguments ディレクティブ](xtypearguments-directive.md)
- [x:Class ディレクティブ](xclass-directive.md)
- [共通の XAML 言語プリミティブの組み込み型](types-for-primitives.md)
