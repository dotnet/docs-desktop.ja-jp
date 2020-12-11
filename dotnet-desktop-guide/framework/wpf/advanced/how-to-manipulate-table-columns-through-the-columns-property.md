---
title: '方法: Columns プロパティによってテーブルの列を操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985032"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="68322-102">方法: Columns プロパティによってテーブルの列を操作する</span><span class="sxs-lookup"><span data-stu-id="68322-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="68322-103">この例では、<xref:System.Windows.Documents.Table.Columns%2A> プロパティを使用して、テーブルの列に対して実行できる一般的な操作をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="68322-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68322-104">例</span><span class="sxs-lookup"><span data-stu-id="68322-104">Example</span></span>  
 <span data-ttu-id="68322-105">次の例では、新しいテーブルを作成し、<xref:System.Windows.Documents.TableColumnCollection.Add%2A> メソッドを使用して、テーブルの <xref:System.Windows.Documents.Table.Columns%2A> コレクションに列を追加します。</span><span class="sxs-lookup"><span data-stu-id="68322-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="68322-106">例</span><span class="sxs-lookup"><span data-stu-id="68322-106">Example</span></span>  
 <span data-ttu-id="68322-107">次の例では、新しい <xref:System.Windows.Documents.TableColumn> を挿入します。</span><span class="sxs-lookup"><span data-stu-id="68322-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="68322-108">新しい列がインデックス位置 0 に挿入され、テーブル内の新しい最初の列になります。</span><span class="sxs-lookup"><span data-stu-id="68322-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68322-109"><xref:System.Windows.Documents.TableColumnCollection> コレクションでは、0 から始まる標準インデックス作成を使用します。</span><span class="sxs-lookup"><span data-stu-id="68322-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="68322-110">例</span><span class="sxs-lookup"><span data-stu-id="68322-110">Example</span></span>  
 <span data-ttu-id="68322-111">次の例では、インデックスによって特定の列を参照して、<xref:System.Windows.Documents.TableColumnCollection> コレクション内の列にある任意のプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="68322-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="68322-112">例</span><span class="sxs-lookup"><span data-stu-id="68322-112">Example</span></span>  
 <span data-ttu-id="68322-113">次の例では、テーブルによって現在ホストされている列の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="68322-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="68322-114">例</span><span class="sxs-lookup"><span data-stu-id="68322-114">Example</span></span>  
 <span data-ttu-id="68322-115">次の例では、参照によって特定の列を削除します。</span><span class="sxs-lookup"><span data-stu-id="68322-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="68322-116">例</span><span class="sxs-lookup"><span data-stu-id="68322-116">Example</span></span>  
 <span data-ttu-id="68322-117">次の例では、インデックスによって特定の列を削除します。</span><span class="sxs-lookup"><span data-stu-id="68322-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="68322-118">例</span><span class="sxs-lookup"><span data-stu-id="68322-118">Example</span></span>  
 <span data-ttu-id="68322-119">次の例では、テーブルの列コレクションからすべての列を削除します。</span><span class="sxs-lookup"><span data-stu-id="68322-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="68322-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="68322-120">See also</span></span>

- [<span data-ttu-id="68322-121">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="68322-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="68322-122">XAML を使用してテーブルを定義する</span><span class="sxs-lookup"><span data-stu-id="68322-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="68322-123">プログラムによってテーブルをビルドする</span><span class="sxs-lookup"><span data-stu-id="68322-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="68322-124">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="68322-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="68322-125">Blocks プロパティを介して FlowDocument を操作する</span><span class="sxs-lookup"><span data-stu-id="68322-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="68322-126">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="68322-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
