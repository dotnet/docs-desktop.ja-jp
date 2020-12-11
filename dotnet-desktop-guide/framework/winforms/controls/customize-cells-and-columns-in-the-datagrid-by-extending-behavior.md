---
title: 動作と外観を拡張して DataGridView コントロールのセルと列をカスタマイズする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- columns [Windows Forms], customizing in DataGridView control
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
ms.openlocfilehash: e111f0bce812fc0851fabd1fde0fc2a6d44dd25f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974245"
---
# <a name="how-to-customize-cells-and-columns-in-the-windows-forms-datagridview-control-by-extending-their-behavior-and-appearance"></a><span data-ttu-id="9ac94-102">方法: Windows フォーム DataGridView コントロールのセルと列を、それぞれの動作と外観を拡張してカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9ac94-102">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>
<span data-ttu-id="9ac94-103"><xref:System.Windows.Forms.DataGridView> コントロールは、プロパティ、イベント、およびコンパニオン クラスを使用して外観と動作をカスタマイズする様々な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-103">The <xref:System.Windows.Forms.DataGridView> control provides a number of ways to customize its appearance and behavior using properties, events, and companion classes.</span></span> <span data-ttu-id="9ac94-104">場合によっては、これらの機能が提供するもの以外にも、セルの要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9ac94-104">Occasionally, you may have requirements for your cells that go beyond what these features can provide.</span></span> <span data-ttu-id="9ac94-105">独自のカスタム <xref:System.Windows.Forms.DataGridViewCell> クラスを作成して、拡張機能を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-105">You can create your own custom <xref:System.Windows.Forms.DataGridViewCell> class to provide extended functionality.</span></span>  
  
 <span data-ttu-id="9ac94-106"><xref:System.Windows.Forms.DataGridViewCell> 基底クラスまたは派生クラスの 1 つから派生することで、カスタム <xref:System.Windows.Forms.DataGridViewCell> クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-106">You create a custom <xref:System.Windows.Forms.DataGridViewCell> class by deriving from the <xref:System.Windows.Forms.DataGridViewCell> base class or one of its derived classes.</span></span> <span data-ttu-id="9ac94-107">任意の種類の列の任意の種類のセルを表示できますが、多くの場合は、セルの種類の表示に特化したカスタムの <xref:System.Windows.Forms.DataGridViewColumn> クラスを作成することになります。</span><span class="sxs-lookup"><span data-stu-id="9ac94-107">Although you can display any type of cell in any type of column, you will typically also create a custom <xref:System.Windows.Forms.DataGridViewColumn> class specialized for displaying your cell type.</span></span> <span data-ttu-id="9ac94-108">列のクラスは、<xref:System.Windows.Forms.DataGridViewColumn> または派生型のいずれかから派生します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-108">Column classes derive from <xref:System.Windows.Forms.DataGridViewColumn> or one of its derived types.</span></span>  
  
 <span data-ttu-id="9ac94-109">次のコード例では、マウスがセルの境界に入ってでるときを検出する、`DataGridViewRolloverCell` と呼ばれるカスタム セル クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-109">In the following code example, you will create a custom cell class called `DataGridViewRolloverCell` that detects when the mouse enters and leaves the cell boundaries.</span></span> <span data-ttu-id="9ac94-110">マウスがセルの範囲内にある場合に、埋め込みの四角形が描画されます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-110">While the mouse is within the cell's bounds, an inset rectangle is drawn.</span></span> <span data-ttu-id="9ac94-111">この新しい型は <xref:System.Windows.Forms.DataGridViewTextBoxCell> から派生して、その他のすべての点では、基底クラスとして動作します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-111">This new type derives from <xref:System.Windows.Forms.DataGridViewTextBoxCell> and behaves in all other respects as its base class.</span></span> <span data-ttu-id="9ac94-112">列のコンパニオン クラスは `DataGridViewRolloverColumn` と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-112">The companion column class is called `DataGridViewRolloverColumn`.</span></span>  
  
 <span data-ttu-id="9ac94-113">これらのクラスを使用するには、<xref:System.Windows.Forms.DataGridView> コントロールを含むフォームを作成して、1 つ以上の `DataGridViewRolloverColumn` オブジェクトを <xref:System.Windows.Forms.DataGridView.Columns%2A> コレクションに追加し、値を含む行にコントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-113">To use these classes, create a form containing a <xref:System.Windows.Forms.DataGridView> control, add one or more `DataGridViewRolloverColumn` objects to the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection, and populate the control with rows containing values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ac94-114">空の行を追加すると、この例は正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="9ac94-114">This example will not work correctly if you add empty rows.</span></span> <span data-ttu-id="9ac94-115">たとえば、<xref:System.Windows.Forms.DataGridView.RowCount%2A> プロパティを設定することでコントロールに行を追加する場合に、空の行を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-115">Empty rows are created, for example, when you add rows to the control by setting the <xref:System.Windows.Forms.DataGridView.RowCount%2A> property.</span></span> <span data-ttu-id="9ac94-116">これは、この例で追加された行は自動的に共有されるためでです。つまり、`DataGridViewRolloverCell` オブジェクトは、各セルをクリックするまでインスタンス化されないため、関連付けられた行の共有が解除されます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-116">This is because the rows added in this case are automatically shared, which means that `DataGridViewRolloverCell` objects are not instantiated until you click on individual cells, thereby causing the associated rows to become unshared.</span></span>  
  
 <span data-ttu-id="9ac94-117">この種類のセルのカスタマイズには共有されていない行が必要なため、大量のデータ セットでの使用には適切ではありません。</span><span class="sxs-lookup"><span data-stu-id="9ac94-117">Because this type of cell customization requires unshared rows, it is not appropriate for use with large data sets.</span></span> <span data-ttu-id="9ac94-118">行の共有の詳細については、「 [Windows フォーム DataGridView コントロールのスケーリングに関するベストプラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac94-118">For more information about row sharing, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ac94-119"><xref:System.Windows.Forms.DataGridViewCell> や <xref:System.Windows.Forms.DataGridViewColumn> から派生したクラスに新しいプロパティを追加するときは、`Clone` メソッドをオーバーライドし、複製操作時に新しいプロパティをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac94-119">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="9ac94-120">また、基底クラスの `Clone` メソッドを呼び出して、基底クラスのプロパティを新しいセルまたは列にコピーする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9ac94-120">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
### <a name="to-customize-cells-and-columns-in-the-datagridview-control"></a><span data-ttu-id="9ac94-121">DataGridView コントロール内でセルと列をカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="9ac94-121">To customize cells and columns in the DataGridView control</span></span>  
  
1. <span data-ttu-id="9ac94-122">`DataGridViewRolloverCell`という新しいセル クラスを <xref:System.Windows.Forms.DataGridViewTextBoxCell> 型から派生させます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-122">Derive a new cell class, called `DataGridViewRolloverCell`, from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2. <span data-ttu-id="9ac94-123"><xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> クラスの `DataGridViewRolloverCell` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="9ac94-123">Override the <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> method in the `DataGridViewRolloverCell` class.</span></span> <span data-ttu-id="9ac94-124">オーバーライドで最初にホストされているテキスト ボックスの機能を処理する基本クラスの実装を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-124">In the override, first call the base class implementation, which handles the hosted text box functionality.</span></span> <span data-ttu-id="9ac94-125">次に、コントロールの <xref:System.Windows.Forms.Control.PointToClient%2A> メソッドを使用して、(画面座標の) カーソル位置を <xref:System.Windows.Forms.DataGridView> クライアント領域の座標に変換します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-125">Then use the control's <xref:System.Windows.Forms.Control.PointToClient%2A> method to transform the cursor position (in screen coordinates) to the <xref:System.Windows.Forms.DataGridView> client area's coordinates.</span></span> <span data-ttu-id="9ac94-126">マウスの座標がセルの境界内にある場合は、埋め込みの四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-126">If the mouse coordinates fall within the bounds of the cell, draw the inset rectangle.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3. <span data-ttu-id="9ac94-127">`DataGridViewRolloverCell` クラスの <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> メソッドと <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> メソッドをオーバーライドして、マウス ポインターがに入る時点または出る時点でセルが自身を再描画するよう強制します。</span><span class="sxs-lookup"><span data-stu-id="9ac94-127">Override the <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> and <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> methods in the `DataGridViewRolloverCell` class to force cells to repaint themselves when the mouse pointer enters or leaves them.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4. <span data-ttu-id="9ac94-128">`DataGridViewRolloverCellColumn` という新しいクラスを <xref:System.Windows.Forms.DataGridViewColumn> 型から派生させます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-128">Derive a new class, called `DataGridViewRolloverCellColumn`, from the <xref:System.Windows.Forms.DataGridViewColumn> type.</span></span> <span data-ttu-id="9ac94-129">コンストラクターで、新しい `DataGridViewRolloverCell` オブジェクトを <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-129">In the constructor, assign a new `DataGridViewRolloverCell` object to its <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## <a name="example"></a><span data-ttu-id="9ac94-130">例</span><span class="sxs-lookup"><span data-stu-id="9ac94-130">Example</span></span>  
 <span data-ttu-id="9ac94-131">完全なコード例には、カスタムのセルの種類の動作を示す小さなテスト フォームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ac94-131">The complete code example includes a small test form that demonstrates the behavior of the custom cell type.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ac94-132">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9ac94-132">Compiling the Code</span></span>  
 <span data-ttu-id="9ac94-133">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9ac94-133">This example requires:</span></span>  
  
- <span data-ttu-id="9ac94-134">System、System.Windows.Forms、および System.Drawing の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="9ac94-134">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ac94-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ac94-135">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="9ac94-136">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="9ac94-136">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9ac94-137">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9ac94-137">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="9ac94-138">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="9ac94-138">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9ac94-139">Windows フォーム DataGridView コントロールを拡張するための推奨される手順</span><span class="sxs-lookup"><span data-stu-id="9ac94-139">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
