---
title: DataGridView コントロールのデータの書式設定
description: Windows フォーム DataGridView コントロールの DefaultCellStyle プロパティと、コントロールの特定の列を使用して、セル値の書式を設定する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 45ae188f92c464e2c8bdb764b9a52f411a497292
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982511"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="24c7c-103">方法: Windows フォーム DataGridView コントロールのデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="24c7c-103">How to: Format Data in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="24c7c-104">次の手順では、コントロール <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> のプロパティ <xref:System.Windows.Forms.DataGridView> とコントロールの特定の列を使用して、セル値の基本的な書式を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24c7c-104">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="24c7c-105">高度なデータ書式設定の詳細については、「 [方法: Windows フォーム DataGridView コントロールでデータの書式設定をカスタマイズする](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24c7c-105">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="24c7c-106">通貨と日付の値を書式設定するには</span><span class="sxs-lookup"><span data-stu-id="24c7c-106">To format currency and date values</span></span>  
  
- <span data-ttu-id="24c7c-107"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="24c7c-107">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="24c7c-108">次のコード例では、列のプロパティを使用して、特定の列の形式を設定し <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="24c7c-108">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="24c7c-109">列の値は、 `UnitPrice` 現在のカルチャ固有の通貨書式で表示され、負の値はかっこで囲まれます。</span><span class="sxs-lookup"><span data-stu-id="24c7c-109">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="24c7c-110">列の値は `ShipDate` 、現在のカルチャに固有の短い日付形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="24c7c-110">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="24c7c-111">値の詳細について <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> は、「 [型の書式設定](/dotnet/standard/base-types/formatting-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24c7c-111">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](/dotnet/standard/base-types/formatting-types).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="24c7c-112">Null データベース値の表示をカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="24c7c-112">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="24c7c-113"><xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="24c7c-113">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="24c7c-114">次のコード例では、プロパティを使用して、 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> と等しい値を含むすべてのセルに "no entry" を表示し <xref:System.DBNull.Value?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="24c7c-114">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="24c7c-115">テキストベースのセルで折り返しを有効にするには</span><span class="sxs-lookup"><span data-stu-id="24c7c-115">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="24c7c-116"><xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>のプロパティを <xref:System.Windows.Forms.DataGridViewCellStyle> 列挙値のいずれかに設定 <xref:System.Windows.Forms.DataGridViewTriState> します。</span><span class="sxs-lookup"><span data-stu-id="24c7c-116">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="24c7c-117">次のコード例では、プロパティを使用して、 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> コントロール全体のラップモードを設定します。</span><span class="sxs-lookup"><span data-stu-id="24c7c-117">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="24c7c-118">DataGridView セルのテキストの配置を指定するには</span><span class="sxs-lookup"><span data-stu-id="24c7c-118">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="24c7c-119"><xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>のプロパティを <xref:System.Windows.Forms.DataGridViewCellStyle> 列挙値のいずれかに設定 <xref:System.Windows.Forms.DataGridViewContentAlignment> します。</span><span class="sxs-lookup"><span data-stu-id="24c7c-119">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="24c7c-120">次のコード例では、列のプロパティを使用して、特定の列の配置を設定し <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="24c7c-120">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="24c7c-121">例</span><span class="sxs-lookup"><span data-stu-id="24c7c-121">Example</span></span>  

 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24c7c-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="24c7c-122">Compiling the Code</span></span>  

 <span data-ttu-id="24c7c-123">これらの例には以下のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="24c7c-123">These examples require:</span></span>  
  
- <span data-ttu-id="24c7c-124">という名前の列、という名前の列、 <xref:System.Windows.Forms.DataGridView> `dataGridView1` およびと `UnitPrice` `ShipDate` いう名前の列を含む、という名前のコントロール `CustomerName` 。</span><span class="sxs-lookup"><span data-stu-id="24c7c-124">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="24c7c-125"><xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="24c7c-125">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="24c7c-126">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="24c7c-126">Robust Programming</span></span>  

 <span data-ttu-id="24c7c-127">最大限のスケーラビリティを実現するには、 <xref:System.Windows.Forms.DataGridViewCellStyle> 各要素のスタイルプロパティを個別に設定するのではなく、同じスタイルを使用する複数の行、列、またはセルでオブジェクトを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24c7c-127">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="24c7c-128">詳細については、「 [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](best-practices-for-scaling-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24c7c-128">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c7c-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="24c7c-129">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="24c7c-130">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="24c7c-130">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="24c7c-131">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="24c7c-131">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="24c7c-132">Windows フォーム DataGridView コントロールでのデータの書式設定</span><span class="sxs-lookup"><span data-stu-id="24c7c-132">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="24c7c-133">方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="24c7c-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="24c7c-134">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="24c7c-134">Formatting Types</span></span>](/dotnet/standard/base-types/formatting-types)
