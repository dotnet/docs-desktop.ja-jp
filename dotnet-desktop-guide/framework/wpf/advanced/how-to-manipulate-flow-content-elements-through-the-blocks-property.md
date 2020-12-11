---
title: '方法: Blocks プロパティを介してフロー コンテンツ要素を操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: 3ca05590bd1adf7f9c486382a08cb334b4731ac9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974965"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="2ca97-102">方法: Blocks プロパティを介してフロー コンテンツ要素を操作する</span><span class="sxs-lookup"><span data-stu-id="2ca97-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="2ca97-103">この例では、**Blocks** プロパティを介して、フロー コンテンツ要素に対して実行できる一般的な操作をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="2ca97-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="2ca97-104">このプロパティは、<xref:System.Windows.Documents.BlockCollection> の項目を追加および削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ca97-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="2ca97-105">**Blocks** プロパティを使用するフロー コンテンツ要素には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="2ca97-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
- <xref:System.Windows.Documents.Figure>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.ListItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="2ca97-106">この例では、フロー コンテンツ要素として <xref:System.Windows.Documents.Section> が使用されることがありますが、これらの手法は、フロー コンテンツ要素コレクションをホストするすべての要素に適用できます。</span><span class="sxs-lookup"><span data-stu-id="2ca97-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ca97-107">例</span><span class="sxs-lookup"><span data-stu-id="2ca97-107">Example</span></span>  
 <span data-ttu-id="2ca97-108">次の例では新しい <xref:System.Windows.Documents.Section> を作成してから、**Add** メソッドを使用して、新しい段落を **Section** コンテンツに追加します。</span><span class="sxs-lookup"><span data-stu-id="2ca97-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="2ca97-109">例</span><span class="sxs-lookup"><span data-stu-id="2ca97-109">Example</span></span>  
 <span data-ttu-id="2ca97-110">次の例では、新しい <xref:System.Windows.Documents.Paragraph> 要素を作成し、それを <xref:System.Windows.Documents.Section> の先頭に挿入します。</span><span class="sxs-lookup"><span data-stu-id="2ca97-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="2ca97-111">例</span><span class="sxs-lookup"><span data-stu-id="2ca97-111">Example</span></span>  
 <span data-ttu-id="2ca97-112">次の例では、<xref:System.Windows.Documents.Section> に含まれる最上位レベルの <xref:System.Windows.Documents.Block> 要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="2ca97-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="2ca97-113">例</span><span class="sxs-lookup"><span data-stu-id="2ca97-113">Example</span></span>  
 <span data-ttu-id="2ca97-114">次の例では、<xref:System.Windows.Documents.Section> 内の最後の <xref:System.Windows.Documents.Block> 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="2ca97-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="2ca97-115">例</span><span class="sxs-lookup"><span data-stu-id="2ca97-115">Example</span></span>  
 <span data-ttu-id="2ca97-116">次の例では、<xref:System.Windows.Documents.Section> からすべてのコンテンツ (<xref:System.Windows.Documents.Block> 要素) をクリアします。</span><span class="sxs-lookup"><span data-stu-id="2ca97-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="2ca97-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ca97-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="2ca97-118">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="2ca97-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="2ca97-119">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="2ca97-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="2ca97-120">Columns プロパティによってテーブルの列を操作する</span><span class="sxs-lookup"><span data-stu-id="2ca97-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="2ca97-121">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="2ca97-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
