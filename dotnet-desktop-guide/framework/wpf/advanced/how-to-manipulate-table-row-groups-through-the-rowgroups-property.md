---
title: '方法: RowGroups プロパティを介してテーブルの行グループを操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: 195920af64888bd3671b45befc0fe4cde463ae7b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985031"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="f5555-102">方法: RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="f5555-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="f5555-103">この例では、<xref:System.Windows.Documents.Table.RowGroups%2A> プロパティを使用して、テーブルの行グループに対して実行できる、より一般的な操作をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f5555-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5555-104">例</span><span class="sxs-lookup"><span data-stu-id="f5555-104">Example</span></span>  
 <span data-ttu-id="f5555-105">次の例では、新しいテーブルを作成し、<xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> メソッドを使用して、テーブルの <xref:System.Windows.Documents.Table.RowGroups%2A> コレクションに列を追加します。</span><span class="sxs-lookup"><span data-stu-id="f5555-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="f5555-106">例</span><span class="sxs-lookup"><span data-stu-id="f5555-106">Example</span></span>  
 <span data-ttu-id="f5555-107">次の例では、新しい <xref:System.Windows.Documents.TableRowGroup> を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f5555-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="f5555-108">新しい列がインデックス位置 0 に挿入され、テーブル内の新しい最初の行グループになります。</span><span class="sxs-lookup"><span data-stu-id="f5555-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5555-109"><xref:System.Windows.Documents.TableRowGroupCollection> コレクションでは、0 から始まる標準インデックス作成を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5555-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="f5555-110">例</span><span class="sxs-lookup"><span data-stu-id="f5555-110">Example</span></span>  
 <span data-ttu-id="f5555-111">次の例では、テーブル内の特定の <xref:System.Windows.Documents.TableRowGroup> (インデックスで指定) に複数の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f5555-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="f5555-112">例</span><span class="sxs-lookup"><span data-stu-id="f5555-112">Example</span></span>  
 <span data-ttu-id="f5555-113">次の例では、テーブル内の最初の行グループの行にある任意のプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f5555-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="f5555-114">例</span><span class="sxs-lookup"><span data-stu-id="f5555-114">Example</span></span>  
 <span data-ttu-id="f5555-115">次の例では、テーブル内の特定の <xref:System.Windows.Documents.TableRow> (インデックスで指定) に複数のセルを追加します。</span><span class="sxs-lookup"><span data-stu-id="f5555-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="f5555-116">例</span><span class="sxs-lookup"><span data-stu-id="f5555-116">Example</span></span>  
 <span data-ttu-id="f5555-117">次の例では、最初の行グループの最初の行のセルにある任意のメソッドとプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f5555-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="f5555-118">例</span><span class="sxs-lookup"><span data-stu-id="f5555-118">Example</span></span>  
 <span data-ttu-id="f5555-119">次の例では、テーブルによってホストされる <xref:System.Windows.Documents.TableRowGroup> 要素の数を返します。</span><span class="sxs-lookup"><span data-stu-id="f5555-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="f5555-120">例</span><span class="sxs-lookup"><span data-stu-id="f5555-120">Example</span></span>  
 <span data-ttu-id="f5555-121">次の例では、参照によって特定の行グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="f5555-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="f5555-122">例</span><span class="sxs-lookup"><span data-stu-id="f5555-122">Example</span></span>  
 <span data-ttu-id="f5555-123">次の例では、インデックスによって特定の行グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="f5555-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="f5555-124">例</span><span class="sxs-lookup"><span data-stu-id="f5555-124">Example</span></span>  
 <span data-ttu-id="f5555-125">次の例では、テーブルの行グループ コレクションからすべての行グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="f5555-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="f5555-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5555-126">See also</span></span>

- [<span data-ttu-id="f5555-127">方法:Inlines プロパティを介してフロー コンテンツ要素を操作する</span><span class="sxs-lookup"><span data-stu-id="f5555-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="f5555-128">Blocks プロパティを介して FlowDocument を操作する</span><span class="sxs-lookup"><span data-stu-id="f5555-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="f5555-129">Columns プロパティによってテーブルの列を操作する</span><span class="sxs-lookup"><span data-stu-id="f5555-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
