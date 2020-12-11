---
title: DataGridView コントロールに交互の行のスタイルを設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: b87ad50ef7e5118a95998949bc62299955856b27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974745"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="7c289-102">方法: Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="7c289-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7c289-103">表形式のデータは、多くの場合、行の背景色が交互に別の色になった、帳簿のような形式でユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c289-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="7c289-104">この形式を使用すると、多数の列がある幅の広いテーブルで、ユーザーが各行にあるセルを簡単に識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7c289-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="7c289-105"><xref:System.Windows.Forms.DataGridView> コントロールを使用すると、1 行おきの完全なスタイル情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c289-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="7c289-106">これにより、背景色だけでなく、前景色とフォントなどのスタイルの特性を使用して、交互の行を区別することができます。</span><span class="sxs-lookup"><span data-stu-id="7c289-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="7c289-107">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7c289-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="7c289-108">「 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c289-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="7c289-109">交互の行のスタイルをプログラムで設定する</span><span class="sxs-lookup"><span data-stu-id="7c289-109">To set alternating row styles programmatically</span></span>  
  
- <span data-ttu-id="7c289-110"><xref:System.Windows.Forms.DataGridView> の <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> プロパティと <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> プロパティにより返される <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7c289-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    > <span data-ttu-id="7c289-111"><xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> プロパティと <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> プロパティを使用して指定したスタイルは、列と <xref:System.Windows.Forms.DataGridView> のレベルで指定されたスタイルをオーバーライドしますが、個別の行とセルのレベルで設定されたスタイルによってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="7c289-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="7c289-112">詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c289-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c289-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7c289-113">Compiling the Code</span></span>  
 <span data-ttu-id="7c289-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7c289-114">This example requires:</span></span>  
  
- <span data-ttu-id="7c289-115">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="7c289-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="7c289-116"><xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7c289-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7c289-117">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="7c289-117">Robust Programming</span></span>  
 <span data-ttu-id="7c289-118">最大限のスケーラビリティを実現するには、各要素のスタイルのプロパティを個別に設定するのではなく、同じスタイルを使用する複数の行、列、またはセルで <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを共有してください。</span><span class="sxs-lookup"><span data-stu-id="7c289-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="7c289-119">詳細については、「 [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](best-practices-for-scaling-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c289-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c289-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c289-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="7c289-121">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="7c289-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7c289-122">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="7c289-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7c289-123">Windows フォーム DataGridView コントロールを拡張するための推奨される手順</span><span class="sxs-lookup"><span data-stu-id="7c289-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7c289-124">方法: Windows フォーム DataGridView コントロールのフォントと色のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="7c289-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
