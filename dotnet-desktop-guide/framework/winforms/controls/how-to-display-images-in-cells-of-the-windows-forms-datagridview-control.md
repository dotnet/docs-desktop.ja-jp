---
title: DataGridView コントロールのセルに画像を表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980836"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="04997-102">方法: Windows フォーム DataGridView コントロールのセルにイメージを表示する</span><span class="sxs-lookup"><span data-stu-id="04997-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="04997-103">画像またはグラフィックは、データ行に表示できる値の1つです。</span><span class="sxs-lookup"><span data-stu-id="04997-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="04997-104">多くの場合、これらのグラフィックは従業員の写真または会社のロゴの形になります。</span><span class="sxs-lookup"><span data-stu-id="04997-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="04997-105">画像の組み込みは、コントロール内にデータを表示するときに簡単に行うことができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="04997-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="04997-106">コントロールは、 <xref:System.Windows.Forms.DataGridView> クラスでサポートされているすべてのイメージ形式に <xref:System.Drawing.Image> 加え、一部のデータベースで使用される OLE ピクチャ形式をネイティブで処理します。</span><span class="sxs-lookup"><span data-stu-id="04997-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="04997-107"><xref:System.Windows.Forms.DataGridView>コントロールのデータソースに画像の列がある場合、コントロールによって自動的に表示され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="04997-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="04997-108">次のコード例では、埋め込みリソースからアイコンを抽出し、イメージ列のすべてのセルに表示するビットマップに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="04997-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="04997-109">テキストのセル値を対応する画像に置き換える別の例については、「 [方法: Windows フォーム DataGridView コントロールでデータの書式をカスタマイズ](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04997-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04997-110">例</span><span class="sxs-lookup"><span data-stu-id="04997-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="04997-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="04997-111">Compiling the Code</span></span>  
 <span data-ttu-id="04997-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="04997-112">This example requires:</span></span>  
  
- <span data-ttu-id="04997-113">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="04997-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="04997-114">という名前の埋め込みアイコンリソース `tree.ico` 。</span><span class="sxs-lookup"><span data-stu-id="04997-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="04997-115"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Drawing?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="04997-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04997-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="04997-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="04997-117">Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能</span><span class="sxs-lookup"><span data-stu-id="04997-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="04997-118">方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="04997-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
