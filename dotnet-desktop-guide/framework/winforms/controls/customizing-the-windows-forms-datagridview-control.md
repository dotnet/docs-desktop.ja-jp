---
title: DataGridView コントロールのカスタマイズ
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974240"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="b3059-102">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b3059-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b3059-103">`DataGridView`コントロールには、セル、行、および列の外観と基本動作 (ルックアンドフィール) を調整するために使用できるいくつかのプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b3059-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="b3059-104">ただし、クラスの機能を超える特別なニーズがある場合 <xref:System.Windows.Forms.DataGridViewCellStyle> は、コントロールのオーナー描画を実装したり、カスタムセル、列、および行を作成してその機能を拡張したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b3059-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="b3059-105">セルと行を自分で描画するには、さまざまな `DataGridView` 描画イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="b3059-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="b3059-106">既存の機能を変更したり、新しい機能を提供したりするには、既存の型、型、および型から派生した独自の型を作成でき `DataGridViewCell` `DataGridViewColumn` `DataGridViewRow` ます。</span><span class="sxs-lookup"><span data-stu-id="b3059-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="b3059-107">また、セルが編集モードのときに選択したコントロールを表示する派生型を作成することによって、新しい編集機能を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3059-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3059-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3059-108">In This Section</span></span>  
 [<span data-ttu-id="b3059-109">方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b3059-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="b3059-110"><xref:System.Windows.Forms.DataGridView.CellPainting>セルを手動で描画するためにイベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3059-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="b3059-111">方法: Windows フォームの DataGridView コントロールの行の外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b3059-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="b3059-112"><xref:System.Windows.Forms.DataGridView.RowPrePaint> <xref:System.Windows.Forms.DataGridView.RowPostPaint> カスタム、グラデーションの背景、および複数の列にまたがるコンテンツを使用して行を描画するために、イベントとイベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3059-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="b3059-113">方法: Windows フォーム DataGridView コントロールのセルと列を、それぞれの動作と外観を拡張してカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b3059-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="b3059-114">およびから派生したカスタム型を作成して `DataGridViewCell` `DataGridViewColumn` 、マウスポインターがセル上にあるときにセルを強調表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3059-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="b3059-115">方法: Windows フォーム DataGridView コントロールのボタン列にあるボタンを無効にする</span><span class="sxs-lookup"><span data-stu-id="b3059-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="b3059-116"><xref:System.Windows.Forms.DataGridViewButtonCell> <xref:System.Windows.Forms.DataGridViewButtonColumn> ボタン列に無効なボタンを表示するために、およびから派生したカスタム型を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3059-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="b3059-117">方法: Windows フォーム DataGridView Cells でコントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="b3059-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="b3059-118">`IDataGridViewEditingControl` `DataGridViewCell` `DataGridViewColumn` <xref:System.Windows.Forms.DateTimePicker> セルが編集モードのときにコントロールを表示するために、インターフェイスを実装し、とから派生したカスタム型を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3059-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b3059-119">リファレンス</span><span class="sxs-lookup"><span data-stu-id="b3059-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="b3059-120"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="b3059-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="b3059-121">クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewCell> します。</span><span class="sxs-lookup"><span data-stu-id="b3059-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="b3059-122">クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewRow> します。</span><span class="sxs-lookup"><span data-stu-id="b3059-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="b3059-123">クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewColumn> します。</span><span class="sxs-lookup"><span data-stu-id="b3059-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="b3059-124">インターフェイスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.IDataGridViewEditingControl> します。</span><span class="sxs-lookup"><span data-stu-id="b3059-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b3059-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3059-125">Related Sections</span></span>  
 [<span data-ttu-id="b3059-126">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="b3059-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b3059-127">コントロールの基本の外観およびセル データの書式設定を変更する方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="b3059-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3059-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3059-128">See also</span></span>

- [<span data-ttu-id="b3059-129">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="b3059-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="b3059-130">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="b3059-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
