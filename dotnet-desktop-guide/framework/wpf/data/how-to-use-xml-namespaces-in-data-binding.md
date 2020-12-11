---
title: '方法: データ バインドで XML 名前空間を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: ad671b81bdfc1c168294123d035ccf7287b3b2fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982612"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="40ad4-102">方法: データ バインドで XML 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="40ad4-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="40ad4-103">例</span><span class="sxs-lookup"><span data-stu-id="40ad4-103">Example</span></span>
 <span data-ttu-id="40ad4-104">この例では、XML のバインディング ソースに指定された名前空間の処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="40ad4-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="40ad4-105">XML データに次の XML 名前空間定義がある場合:</span><span class="sxs-lookup"><span data-stu-id="40ad4-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="40ad4-106">次の例で示すように、<xref:System.Windows.Data.XmlNamespaceMapping> 要素を使用して、名前空間を <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> にマップできます。</span><span class="sxs-lookup"><span data-stu-id="40ad4-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="40ad4-107">その後、<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> を使用して、XML 名前空間を参照できます。</span><span class="sxs-lookup"><span data-stu-id="40ad4-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="40ad4-108">この例の <xref:System.Windows.Controls.ListBox> には、各 *item* の *title* と *dc:date* が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40ad4-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="40ad4-109">指定する <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> は、XML ソースで使用されているものと一致する必要はありません。XML ソースでプレフィックスが変更された場合でも、マッピングは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="40ad4-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="40ad4-110">この特定の例では、XML データは Web サービスから取得されますが、<xref:System.Windows.Data.XmlNamespaceMapping> 要素は、インラインの XML でも、埋め込まれているファイルの XML データでも有効です。</span><span class="sxs-lookup"><span data-stu-id="40ad4-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="40ad4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="40ad4-111">See also</span></span>

- [<span data-ttu-id="40ad4-112">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="40ad4-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="40ad4-113">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="40ad4-113">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="40ad4-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="40ad4-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
