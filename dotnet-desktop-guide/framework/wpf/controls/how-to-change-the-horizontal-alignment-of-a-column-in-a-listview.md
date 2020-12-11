---
title: '方法: ListView の列の水平方向の配置を変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: cdf479fc9f84f88fccc877e9fdf8ca56d53c1c4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984455"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="23cbd-102">方法: ListView の列の水平方向の配置を変更する</span><span class="sxs-lookup"><span data-stu-id="23cbd-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="23cbd-103">既定では、<xref:System.Windows.Controls.ListViewItem> の各列のコンテンツは左揃えになっています。</span><span class="sxs-lookup"><span data-stu-id="23cbd-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="23cbd-104">各列の配置を変更するには、<xref:System.Windows.DataTemplate> を指定して、<xref:System.Windows.DataTemplate> 内の要素の <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="23cbd-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="23cbd-105">このトピックでは、<xref:System.Windows.Controls.ListView> が既定でどのようにコンテンツを配置するのかについてと、<xref:System.Windows.Controls.ListView> 内の 1 つの列の配置を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23cbd-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23cbd-106">例</span><span class="sxs-lookup"><span data-stu-id="23cbd-106">Example</span></span>  
 <span data-ttu-id="23cbd-107">次の例では、`Title` 列と `ISBN` 列のデータが左揃えになっています。</span><span class="sxs-lookup"><span data-stu-id="23cbd-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="23cbd-108">`ISBN` 列の配置を変更するには、各 <xref:System.Windows.Controls.ListViewItem> の <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> プロパティが <xref:System.Windows.HorizontalAlignment.Stretch> となるように指定する必要があります。これにより、各 <xref:System.Windows.Controls.ListViewItem> 内の要素は、各列の幅全体にわたって、または幅全体に沿って配置されます。</span><span class="sxs-lookup"><span data-stu-id="23cbd-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="23cbd-109"><xref:System.Windows.Controls.ListView> はデータ ソースにバインドされるため、<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> を設定するスタイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23cbd-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="23cbd-110">次に、<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> プロパティを使用する代わりに、<xref:System.Windows.DataTemplate> を使用してコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23cbd-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="23cbd-111">各テンプレートの `ISBN` を表示するには、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティが <xref:System.Windows.HorizontalAlignment.Right> に設定されている <xref:System.Windows.Controls.TextBlock> のみを <xref:System.Windows.DataTemplate> に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="23cbd-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="23cbd-112">次の例では、`ISBN` 列を右揃えにするために必要なスタイルと <xref:System.Windows.DataTemplate> を定義し、<xref:System.Windows.DataTemplate> を参照するように <xref:System.Windows.Controls.GridViewColumn> を変更します。</span><span class="sxs-lookup"><span data-stu-id="23cbd-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="23cbd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="23cbd-113">See also</span></span>

- [<span data-ttu-id="23cbd-114">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="23cbd-114">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="23cbd-115">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="23cbd-115">Data Templating Overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="23cbd-116">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="23cbd-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="23cbd-117">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="23cbd-117">ListView Overview</span></span>](listview-overview.md)
