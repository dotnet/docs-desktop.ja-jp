---
title: '方法: プログラムによってテーブルをビルドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 586bff2e0aa1a545dc070a8bab2cdc6ed9a104ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982283"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="ca142-102">方法: プログラムによってテーブルをビルドする</span><span class="sxs-lookup"><span data-stu-id="ca142-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="ca142-103">次の例は、プログラムで <xref:System.Windows.Documents.Table> を作成して内容を格納する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ca142-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="ca142-104">テーブルの内容は 5 つの行 (<xref:System.Windows.Documents.Table.RowGroups%2A> オブジェクトに含まれる <xref:System.Windows.Documents.TableRow> オブジェクトにより表される) と 6 つの列 (<xref:System.Windows.Documents.TableColumn> オブジェクトにより表される) に配分されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="ca142-105">たとえば、タイトル行はテーブル全体のタイトルの設定に使用され、ヘッダー行はテーブル内のデータ列の説明、フッター行は要約情報の格納に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="ca142-106">"タイトル"、"ヘッダー"、"フッター" 行の概念はテーブルに固有のものではなく、単純に異なる特性を持つ行です。</span><span class="sxs-lookup"><span data-stu-id="ca142-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="ca142-107">テーブルのセルには実際の内容が格納されます。テキスト、画像、またはその他のほとんどすべての [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 要素を格納できます。</span><span class="sxs-lookup"><span data-stu-id="ca142-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca142-108">例</span><span class="sxs-lookup"><span data-stu-id="ca142-108">Example</span></span>  
 <span data-ttu-id="ca142-109">まず、<xref:System.Windows.Documents.Table> をホストする <xref:System.Windows.Documents.FlowDocument> が作成され、新しい <xref:System.Windows.Documents.Table> が作成され、<xref:System.Windows.Documents.FlowDocument> の内容に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="ca142-110">例</span><span class="sxs-lookup"><span data-stu-id="ca142-110">Example</span></span>  
 <span data-ttu-id="ca142-111">次に、6 つの <xref:System.Windows.Documents.TableColumn> オブジェクトが作成されてテーブルの <xref:System.Windows.Documents.Table.Columns%2A> に追加され、いくつかの書式設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca142-112">テーブルの <xref:System.Windows.Documents.Table.Columns%2A> コレクションでは、0 から始まる標準インデックス作成が使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca142-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="ca142-113">例</span><span class="sxs-lookup"><span data-stu-id="ca142-113">Example</span></span>  
 <span data-ttu-id="ca142-114">次に、タイトル行が作成され、テーブルに追加されます。いくつかの書式設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="ca142-115">タイトル行には、テーブルの 6 つの列にまたがる 1 つのセルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="ca142-116">例</span><span class="sxs-lookup"><span data-stu-id="ca142-116">Example</span></span>  
 <span data-ttu-id="ca142-117">次に、ヘッダー行を作成してテーブルに追加し、ヘッダー行のセルを作成してデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="ca142-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="ca142-118">例</span><span class="sxs-lookup"><span data-stu-id="ca142-118">Example</span></span>  
 <span data-ttu-id="ca142-119">次に、データの行が作成され、テーブルに追加されます。この行のセルが作成され、内容が入力されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="ca142-120">この行の作成はヘッダー行の作成に似ていますが、適用する書式が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="ca142-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="ca142-121">例</span><span class="sxs-lookup"><span data-stu-id="ca142-121">Example</span></span>  
 <span data-ttu-id="ca142-122">最後に、フッター行が作成され、追加され、書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="ca142-123">タイトル行と同様に、フッター行にはテーブルの 6 つの列にまたがる 1 つのセルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="ca142-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="ca142-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca142-124">See also</span></span>

- [<span data-ttu-id="ca142-125">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="ca142-125">Table Overview</span></span>](table-overview.md)
