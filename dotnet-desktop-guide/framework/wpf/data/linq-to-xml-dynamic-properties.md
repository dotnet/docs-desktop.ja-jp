---
title: LINQ to XML の動的プロパティ リファレンス
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: ca3684716f9b562d0e6a006c26730a1d1a28f8b1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981439"
---
# <a name="linq-to-xml-dynamic-properties"></a><span data-ttu-id="e2124-102">LINQ to XML の動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="e2124-102">LINQ to XML dynamic properties</span></span>

<span data-ttu-id="e2124-103">ここでは、LINQ to XML の動的プロパティに関する参照情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2124-103">This section provides reference information about the dynamic properties in LINQ to XML.</span></span> <span data-ttu-id="e2124-104">これらのプロパティは、具体的には <xref:System.Xml.Linq.XAttribute> 名前空間の <xref:System.Xml.Linq.XElement> クラスと <xref:System.Xml.Linq> クラスによって公開されます。</span><span class="sxs-lookup"><span data-stu-id="e2124-104">Specifically, these properties are exposed by the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, which are in the <xref:System.Xml.Linq> namespace.</span></span>

<span data-ttu-id="e2124-105">「[LINQ to XML による WPF のデータ バインディングの概要](wpf-data-binding-with-linq-to-xml-overview.md)」のトピックで説明されているように、各動的プロパティには、対応する標準のパブリック プロパティやパブリック メソッドが同じクラスにあります。</span><span class="sxs-lookup"><span data-stu-id="e2124-105">As explained in the topic [Overview of WPF data binding with LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), each of the dynamic properties is equivalent to a standard public property or method in the same class.</span></span> <span data-ttu-id="e2124-106">ほとんどの用途では、これらの標準のメンバーを使用する必要があります。動的プロパティは、LINQ to XML のデータ バインドのシナリオ専用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="e2124-106">These standard members should be used for most purposes; dynamic properties are provided specifically for LINQ to XML data binding scenarios.</span></span> <span data-ttu-id="e2124-107">これらのクラスの標準のメンバーに関する詳細については、リファレンス トピックの「<xref:System.Xml.Linq.XAttribute>」および「<xref:System.Xml.Linq.XElement>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2124-107">For more information about the standard members of these classes, see the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> reference topics.</span></span>

<span data-ttu-id="e2124-108">このセクションの動的プロパティは、解決される値に関連して次の 2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="e2124-108">With respect to their resolved values, the dynamic properties in this section fall into two categories:</span></span>

- <span data-ttu-id="e2124-109">1 つの値に解決される単純なプロパティ (`Value` クラスや <xref:System.Xml.Linq.XAttribute> クラスの <xref:System.Xml.Linq.XElement> プロパティなど)。</span><span class="sxs-lookup"><span data-stu-id="e2124-109">Simple ones, such as the `Value` properties in the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, that resolve to a single value.</span></span>

- <span data-ttu-id="e2124-110">インデクサー型に解決されるインデックス値 (<xref:System.Xml.Linq.XElement> の [Elements](elements-xelement-dynamic-property.md) プロパティや [Descendants](descendants-xelement-dynamic-property.md) プロパティなど)。</span><span class="sxs-lookup"><span data-stu-id="e2124-110">Indexed values, such as the [Elements](elements-xelement-dynamic-property.md) and [Descendants](descendants-xelement-dynamic-property.md) properties of <xref:System.Xml.Linq.XElement>, that resolve into an indexer type.</span></span> <span data-ttu-id="e2124-111">インデクサー型が目的の値やコレクションに解決されるようにするには、拡張名のパラメーターを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2124-111">For indexer types to be resolved to the desired value or collection, an expanded name parameter must be passed to them.</span></span>

<span data-ttu-id="e2124-112"><xref:System.Collections.Generic.IEnumerable%601> 型のインデックス値を返す動的プロパティはすべて遅延実行を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2124-112">All the dynamic properties that return an indexed value of type <xref:System.Collections.Generic.IEnumerable%601> use deferred execution.</span></span> <span data-ttu-id="e2124-113">遅延実行について詳しくは、「[LINQ クエリの概要 (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2124-113">For more information about deferred execution, see [Introduction to LINQ queries (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).</span></span>

## <a name="reference"></a><span data-ttu-id="e2124-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2124-114">Reference</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a><span data-ttu-id="e2124-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2124-115">See also</span></span>

- [<span data-ttu-id="e2124-116">LINQ to XML による WPF のデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="e2124-116">WPF data binding with LINQ to XML</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="e2124-117">LINQ to XML による WPF のデータ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="e2124-117">WPF data binding with LINQ to XML overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="e2124-118">LINQ クエリの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="e2124-118">Introduction to LINQ queries (C#)</span></span>](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
