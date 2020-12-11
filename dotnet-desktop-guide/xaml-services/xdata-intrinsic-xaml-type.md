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
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="81b08-102">x:XData 組み込み XAML 型</span><span class="sxs-lookup"><span data-stu-id="81b08-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="81b08-103">XAML 運用環境内での XML データアイランドの配置を有効にします。</span><span class="sxs-lookup"><span data-stu-id="81b08-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="81b08-104">内の XML 要素は、 `x:XData` 動作する既定の xaml 名前空間またはその他の xaml 名前空間の一部であるかのように、xaml プロセッサによって処理されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81b08-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="81b08-105">`x:XData` 任意の整形式の XML を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="81b08-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="81b08-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="81b08-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="81b08-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="81b08-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="81b08-108">囲まれたデータアイランドの単一のルート要素。</span><span class="sxs-lookup"><span data-stu-id="81b08-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="81b08-109">最終的なコンシューマーの多くは、1つのルートを持たない XML は無効と見なされます。</span><span class="sxs-lookup"><span data-stu-id="81b08-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="81b08-110">特に、 `x:XData` が WPF の xml データソースである場合、またはデータバインディングに xml ソースを使用するその他の多くのテクノロジの場合は、単一のルートが必要です。</span><span class="sxs-lookup"><span data-stu-id="81b08-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="81b08-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="81b08-111">Optional.</span></span> <span data-ttu-id="81b08-112">XML データを表す XML です。</span><span class="sxs-lookup"><span data-stu-id="81b08-112">XML that represents the XML data.</span></span> <span data-ttu-id="81b08-113">要素データとして任意の数の要素を含めることができ、入れ子になった要素を他の要素に含めることができます。ただし、XML の一般的な規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="81b08-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="81b08-114">注釈</span><span class="sxs-lookup"><span data-stu-id="81b08-114">Remarks</span></span>

<span data-ttu-id="81b08-115">オブジェクト内の XML 要素は、 `x:XData` データ内の格納されている XMLDOM のすべての可能な名前空間とプレフィックスを再宣言できます。</span><span class="sxs-lookup"><span data-stu-id="81b08-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="81b08-116">`x:XData`.NET Xaml サービスでは、クラスを使用して、プログラムで XML データと組み込み xaml 型にアクセスでき <xref:System.Windows.Markup.XData> ます。</span><span class="sxs-lookup"><span data-stu-id="81b08-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="81b08-117">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="81b08-117">WPF Usage Notes</span></span>

<span data-ttu-id="81b08-118">`x:XData`オブジェクトは、主にの子オブジェクトとして使用されるか、またはプロパティの子オブジェクトとして使用され <xref:System.Windows.Data.XmlDataProvider> <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ます (XAML では、これは通常、プロパティ要素構文で表されます)。</span><span class="sxs-lookup"><span data-stu-id="81b08-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="81b08-119">データは、通常、データアイランド内の基本 XML 名前空間を新しい既定の XML 名前空間 (空の文字列に設定) に再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81b08-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="81b08-120"><xref:System.Windows.Data.Binding.XPath%2A>データの参照とバインドに使用される式ではプレフィックスが含まれないため、単純なデータアイランドではこの方法が最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="81b08-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="81b08-121">より複雑なデータアイランドでは、データに複数のプレフィックスを定義し、ルートで XML 名前空間に特定のプレフィックスを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="81b08-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="81b08-122">この場合、すべての <xref:System.Windows.Data.Binding.XPath%2A> 式参照には、適切な名前空間にマップされたプレフィックスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="81b08-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="81b08-123">詳しくは、「 [データ バインディングの概要](../net/wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="81b08-123">For more information, see [Data Binding Overview](../net/wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="81b08-124">技術的には、 `x:XData` 型の任意のプロパティのコンテンツとして使用でき <xref:System.Xml.Serialization.IXmlSerializable> ます。</span><span class="sxs-lookup"><span data-stu-id="81b08-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="81b08-125">ただし、 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> は唯一の実装です。</span><span class="sxs-lookup"><span data-stu-id="81b08-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="81b08-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="81b08-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="81b08-127">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="81b08-127">Data Binding Overview</span></span>](../net/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="81b08-128">バインドのマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="81b08-128">Binding Markup Extension</span></span>](../framework/wpf/advanced/binding-markup-extension.md)
