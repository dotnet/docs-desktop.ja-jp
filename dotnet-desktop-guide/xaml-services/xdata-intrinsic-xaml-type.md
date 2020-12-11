---
title: x:XData 組み込み XAML 型
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 89bdae68608db235b76d6a9b210c77f97bcebe00
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980155"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 組み込み XAML 型
XAML 運用環境内での XML データアイランドの配置を有効にします。 内の XML 要素は、 `x:XData` 動作する既定の xaml 名前空間またはその他の xaml 名前空間の一部であるかのように、xaml プロセッサによって処理されないようにする必要があります。 `x:XData` 任意の整形式の XML を含めることができます。

## <a name="xaml-object-element-usage"></a>XAML オブジェクト要素の使用方法

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`elementDataRoot`|囲まれたデータアイランドの単一のルート要素。 最終的なコンシューマーの多くは、1つのルートを持たない XML は無効と見なされます。 特に、 `x:XData` が WPF の xml データソースである場合、またはデータバインディングに xml ソースを使用するその他の多くのテクノロジの場合は、単一のルートが必要です。|
|`[elementData]`|省略可能。 XML データを表す XML です。 要素データとして任意の数の要素を含めることができ、入れ子になった要素を他の要素に含めることができます。ただし、XML の一般的な規則が適用されます。|

## <a name="remarks"></a>注釈

オブジェクト内の XML 要素は、 `x:XData` データ内の格納されている XMLDOM のすべての可能な名前空間とプレフィックスを再宣言できます。

`x:XData`.NET Xaml サービスでは、クラスを使用して、プログラムで XML データと組み込み xaml 型にアクセスでき <xref:System.Windows.Markup.XData> ます。

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

`x:XData`オブジェクトは、主にの子オブジェクトとして使用されるか、またはプロパティの子オブジェクトとして使用され <xref:System.Windows.Data.XmlDataProvider> <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ます (XAML では、これは通常、プロパティ要素構文で表されます)。

データは、通常、データアイランド内の基本 XML 名前空間を新しい既定の XML 名前空間 (空の文字列に設定) に再定義する必要があります。 <xref:System.Windows.Data.Binding.XPath%2A>データの参照とバインドに使用される式ではプレフィックスが含まれないため、単純なデータアイランドではこの方法が最も簡単です。 より複雑なデータアイランドでは、データに複数のプレフィックスを定義し、ルートで XML 名前空間に特定のプレフィックスを使用する場合があります。 この場合、すべての <xref:System.Windows.Data.Binding.XPath%2A> 式参照には、適切な名前空間にマップされたプレフィックスが含まれている必要があります。 詳しくは、「 [データ バインディングの概要](../net/wpf/data/data-binding-overview.md)」をご覧ください。

技術的には、 `x:XData` 型の任意のプロパティのコンテンツとして使用でき <xref:System.Xml.Serialization.IXmlSerializable> ます。 ただし、 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> は唯一の実装です。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Data.XmlDataProvider>
- [データ バインディングの概要](../net/wpf/data/data-binding-overview.md)
- [バインドのマークアップ拡張機能](../framework/wpf/advanced/binding-markup-extension.md)
