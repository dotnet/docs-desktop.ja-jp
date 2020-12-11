---
title: '方法: XDocument、XElement、または LINQ for XML クエリの結果にバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984184"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="5e7fe-102">方法: XDocument、XElement、または LINQ for XML クエリの結果にバインドする</span><span class="sxs-lookup"><span data-stu-id="5e7fe-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>

<span data-ttu-id="5e7fe-103">この例では、<xref:System.Xml.Linq.XDocument> を使用して XML データを <xref:System.Windows.Controls.ItemsControl> にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>

## <a name="example"></a><span data-ttu-id="5e7fe-104">例</span><span class="sxs-lookup"><span data-stu-id="5e7fe-104">Example</span></span>

<span data-ttu-id="5e7fe-105">次の XAML コードでは、<xref:System.Windows.Controls.ItemsControl> を定義し、`Planet` 型のデータ用のデータ テンプレートを `http://planetsNS` XML 名前空間に含めます。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="5e7fe-106">名前空間を占有する XML データ型では、名前空間をかっこで囲んで含める必要があります。また、その XML データ型が、XAML マークアップ拡張機能が出現する可能性がある場所に出現する場合は、名前空間の前に、かっこのエスケープ シーケンスを使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="5e7fe-107">このコードでは、<xref:System.Xml.Linq.XElement> クラスの <xref:System.Xml.Linq.XContainer.Element%2A> および <xref:System.Xml.Linq.XElement.Attribute%2A> メソッドに対応する動的プロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="5e7fe-108">動的プロパティによって、XAML がこれらのメソッドの名前を共有する動的プロパティにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="5e7fe-109">詳しくは、「[LINQ to XML の動的プロパティ](linq-to-xml-dynamic-properties.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-109">To learn more, see [LINQ to XML dynamic properties](linq-to-xml-dynamic-properties.md).</span></span> <span data-ttu-id="5e7fe-110">XML 用の既定の名前空間宣言が属性名には適用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

<span data-ttu-id="5e7fe-111">次の C# コードでは、<xref:System.Xml.Linq.XDocument.Load%2A> を呼び出して、スタック パネルのデータ コンテキストを、`http://planetsNS` XML 名前空間内の `SolarSystemPlanets` という名前の要素のすべてのサブ要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

<span data-ttu-id="5e7fe-112">XML データは、<xref:System.Windows.Data.ObjectDataProvider> を使用して XAML リソースとして格納できます。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="5e7fe-113">コード例全体については、「[L2DBForm.xaml ソース コード](l2dbform-xaml-source-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-113">For a complete example, see  [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="5e7fe-114">次の例は、コードでデータ コンテキストをオブジェクト リソースに設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-114">The following sample shows how code can set the data context to an object resource.</span></span>

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

<span data-ttu-id="5e7fe-115"><xref:System.Xml.Linq.XContainer.Element%2A> および <xref:System.Xml.Linq.XElement.Attribute%2A> に動的プロパティをマップすることによって、XAML 内での柔軟性が増します。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="5e7fe-116">コードを LINQ for XML クエリの結果にバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="5e7fe-117">この例は、要素の値によって並べられたクエリ結果にバインドします。</span><span class="sxs-lookup"><span data-stu-id="5e7fe-117">This example binds to query results ordered by an element value.</span></span>

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a><span data-ttu-id="5e7fe-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e7fe-118">See also</span></span>

- [<span data-ttu-id="5e7fe-119">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="5e7fe-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="5e7fe-120">LINQ to XML による WPF のデータ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="5e7fe-120">WPF Data Binding with LINQ to XML Overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="5e7fe-121">LINQ to XML を使用した WPF のデータ バインディングの例</span><span class="sxs-lookup"><span data-stu-id="5e7fe-121">WPF Data Binding Using LINQ to XML Example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="5e7fe-122">LINQ to XML の動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="5e7fe-122">LINQ to XML Dynamic Properties</span></span>](linq-to-xml-dynamic-properties.md)
