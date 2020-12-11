---
title: x:Reference のマークアップ拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980095"
---
# <a name="xreference-markup-extension"></a>x:Reference のマークアップ拡張機能

XAML マークアップの他の場所で宣言されているインスタンスを参照します。 参照が要素のを参照して `x:Name` います。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>XAML オブジェクト要素の使用方法

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`instancexName`|参照された `x:Name` インスタンスの値 (または、指定されたプロパティの値 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> )。|

## <a name="remarks"></a>注釈

`x:Reference` WPF などの特定のフレームワークで実装されていた要素参照の概念に対する XAML 言語レベルのサポートを提供します。

## <a name="xreference-and-wpf"></a>x:Reference と WPF

WPF および XAML 2006 では、要素参照は、バインディングのフレームワークレベルの機能によってアドレス指定され <xref:System.Windows.Data.Binding.ElementName%2A> ます。 ほとんどの WPF アプリケーションとシナリオでは、 <xref:System.Windows.Data.Binding.ElementName%2A> バインドを使用する必要があります。 この一般的なガイダンスの例外として、データコンテキストがある場合や、データバインディングが実用的ではなく、マークアップコンパイルが関係しない場合などがあります。

`x:Reference` は、XAML 2009 で定義されている構造体です。 WPF では XAML 2009 の機能を使用できますが、WPF マークアップ コンパイルされていない XAML に限定されます。 マークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 言語のキーワードと機能をサポートしていません。
