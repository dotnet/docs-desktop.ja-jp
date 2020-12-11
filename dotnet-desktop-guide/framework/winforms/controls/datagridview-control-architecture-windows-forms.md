---
title: DataGridView コントロールのアーキテクチャ
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974223"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="d6122-102">DataGridView コントロールのアーキテクチャ (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d6122-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="d6122-103"><xref:System.Windows.Forms.DataGridView>コントロールとその関連クラスは、表形式データを表示および編集するための柔軟で拡張可能なシステムとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="d6122-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="d6122-104">これらのクラスはすべて、名前空間に含まれ <xref:System.Windows.Forms?displayProperty=nameWithType> ており、すべて "DataGridView" プレフィックスで名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="d6122-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="d6122-105">アーキテクチャの要素</span><span class="sxs-lookup"><span data-stu-id="d6122-105">Architecture Elements</span></span>  
 <span data-ttu-id="d6122-106">プライマリ <xref:System.Windows.Forms.DataGridView> コンパニオンクラスは、から派生 <xref:System.Windows.Forms.DataGridViewElement> します。</span><span class="sxs-lookup"><span data-stu-id="d6122-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="d6122-107">次のオブジェクトモデルは、継承階層を示してい <xref:System.Windows.Forms.DataGridViewElement> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![DataGridViewElement オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="d6122-109">クラスは、 <xref:System.Windows.Forms.DataGridViewElement> 親コントロールへの参照を提供 <xref:System.Windows.Forms.DataGridView> し、プロパティを持ち <xref:System.Windows.Forms.DataGridViewElement.State%2A> ます。このプロパティには、列挙体の値の組み合わせを表す値が格納され <xref:System.Windows.Forms.DataGridViewElementStates> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="d6122-110">以下のセクションでは、関連するクラスについて詳しく説明し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="d6122-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="d6122-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="d6122-112"><xref:System.Windows.Forms.DataGridViewElementStates> 列挙体には次の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6122-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="d6122-113">この列挙体の値はビットごとの論理演算子と組み合わせることができるため、 <xref:System.Windows.Forms.DataGridViewElement.State%2A> プロパティは一度に複数の状態を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="d6122-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="d6122-114">たとえば、は <xref:System.Windows.Forms.DataGridViewElement> 同時に、、およびにすることができ <xref:System.Windows.Forms.DataGridViewElementStates.Frozen> <xref:System.Windows.Forms.DataGridViewElementStates.Selected> <xref:System.Windows.Forms.DataGridViewElementStates.Visible> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="d6122-115">セルとバンド</span><span class="sxs-lookup"><span data-stu-id="d6122-115">Cells and Bands</span></span>  
 <span data-ttu-id="d6122-116">コントロールは、 <xref:System.Windows.Forms.DataGridView> セルとバンドの2つの基本的な種類のオブジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d6122-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="d6122-117">すべてのセルは、 <xref:System.Windows.Forms.DataGridViewCell> 基本クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="d6122-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="d6122-118">2種類のバンド ( <xref:System.Windows.Forms.DataGridViewColumn> と) は、 <xref:System.Windows.Forms.DataGridViewRow> どちらも基本クラスから派生し <xref:System.Windows.Forms.DataGridViewBand> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="d6122-119"><xref:System.Windows.Forms.DataGridView>コントロールは複数のクラスと相互運用しますが、最も一般的に発生するのは、、、 <xref:System.Windows.Forms.DataGridViewCell> <xref:System.Windows.Forms.DataGridViewColumn> <xref:System.Windows.Forms.DataGridViewRow> です。</span><span class="sxs-lookup"><span data-stu-id="d6122-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="d6122-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="d6122-120">DataGridViewCell</span></span>  
 <span data-ttu-id="d6122-121">セルは、の相互作用の基本単位です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="d6122-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="d6122-122">表示はセルの中央に配置され、多くの場合、データ入力はセルを通じて実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6122-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="d6122-123">クラスのコレクションを使用してセルにアクセスでき <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> <xref:System.Windows.Forms.DataGridViewRow> ます。また、コントロールのコレクションを使用して、選択したセルにアクセスでき <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d6122-124">次のオブジェクトモデルは、この使用方法を示し、継承階層を示してい <xref:System.Windows.Forms.DataGridViewCell> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![DataGridViewCell オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="d6122-126">この <xref:System.Windows.Forms.DataGridViewCell> 型は、すべてのセル型の派生元である抽象基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="d6122-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="d6122-127"><xref:System.Windows.Forms.DataGridViewCell> とその派生型は Windows フォームコントロールではなく、一部のホスト Windows フォームコントロールです。</span><span class="sxs-lookup"><span data-stu-id="d6122-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="d6122-128">セルでサポートされる編集機能は、通常、ホストされるコントロールによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d6122-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="d6122-129"><xref:System.Windows.Forms.DataGridViewCell> オブジェクトは、Windows フォームコントロールと同じように、独自の外観および描画機能を制御しません。</span><span class="sxs-lookup"><span data-stu-id="d6122-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="d6122-130">代わりに、は <xref:System.Windows.Forms.DataGridView> オブジェクトの外観を担い <xref:System.Windows.Forms.DataGridViewCell> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="d6122-131">コントロールのプロパティとイベントを操作することによって、セルの外観と動作に大きな影響を与えることができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="d6122-132">コントロールの機能を超えるカスタマイズに特別な要件がある場合 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewCell> は、またはその子クラスの1つから派生する独自のクラスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="d6122-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="d6122-133">から派生したクラスを次に示し <xref:System.Windows.Forms.DataGridViewCell> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="d6122-134">カスタムセルの種類</span><span class="sxs-lookup"><span data-stu-id="d6122-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="d6122-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="d6122-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="d6122-136"><xref:System.Windows.Forms.DataGridView>コントロールのアタッチされたデータストアのスキーマは、コントロールの列で表現され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="d6122-137"><xref:System.Windows.Forms.DataGridView>コントロールの列にアクセスするには、コレクションを使用し <xref:System.Windows.Forms.DataGridView.Columns%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="d6122-138">選択した列には、コレクションを使用してアクセスでき <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="d6122-139">次のオブジェクトモデルは、この使用方法を示し、継承階層を示してい <xref:System.Windows.Forms.DataGridViewColumn> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![DataGridViewColumn オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="d6122-141">主なセル型には、対応する列の型があります。</span><span class="sxs-lookup"><span data-stu-id="d6122-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="d6122-142">これらは <xref:System.Windows.Forms.DataGridViewColumn> 基本クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="d6122-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="d6122-143">から派生したクラスを次に示し <xref:System.Windows.Forms.DataGridViewColumn> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="d6122-144">カスタム列の型</span><span class="sxs-lookup"><span data-stu-id="d6122-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="d6122-145">DataGridView 編集コントロール</span><span class="sxs-lookup"><span data-stu-id="d6122-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="d6122-146">高度な編集機能をサポートするセルは、通常、Windows フォームコントロールから派生したホストされたコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6122-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="d6122-147">これらのコントロールは、 <xref:System.Windows.Forms.IDataGridViewEditingControl> インターフェイスも実装します。</span><span class="sxs-lookup"><span data-stu-id="d6122-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="d6122-148">次のオブジェクトモデルは、これらのコントロールの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6122-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![DataGridView 編集コントロールオブジェクトモデルの階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="d6122-150">コントロールには、次の編集コントロールが用意されてい <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="d6122-151">独自の編集コントロールを作成する方法については、「 [方法: Windows フォーム DataGridView セルのコントロールをホスト](how-to-host-controls-in-windows-forms-datagridview-cells.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6122-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="d6122-152">次の表は、セルの種類、列の種類、および編集コントロールの関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6122-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="d6122-153">セルの種類</span><span class="sxs-lookup"><span data-stu-id="d6122-153">Cell type</span></span>|<span data-ttu-id="d6122-154">ホストされるコントロール</span><span class="sxs-lookup"><span data-stu-id="d6122-154">Hosted control</span></span>|<span data-ttu-id="d6122-155">列の型</span><span class="sxs-lookup"><span data-stu-id="d6122-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="d6122-156">該当なし</span><span class="sxs-lookup"><span data-stu-id="d6122-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="d6122-157">該当なし</span><span class="sxs-lookup"><span data-stu-id="d6122-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="d6122-158">該当なし</span><span class="sxs-lookup"><span data-stu-id="d6122-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="d6122-159">該当なし</span><span class="sxs-lookup"><span data-stu-id="d6122-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="d6122-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="d6122-160">DataGridViewRow</span></span>  
 <span data-ttu-id="d6122-161">クラスは、コントロールがアタッチされている <xref:System.Windows.Forms.DataGridViewRow> データストアのレコードのデータフィールドを表示し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="d6122-162"><xref:System.Windows.Forms.DataGridView>コントロールの行にアクセスするには、コレクションを使用し <xref:System.Windows.Forms.DataGridView.Rows%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="d6122-163">選択した行には、コレクションを使用してアクセスでき <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="d6122-164">次のオブジェクトモデルは、この使用方法を示し、継承階層を示してい <xref:System.Windows.Forms.DataGridViewRow> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![DataGridViewRow オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="d6122-166">クラスから独自の型を派生させることもできますが、 <xref:System.Windows.Forms.DataGridViewRow> 通常は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d6122-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="d6122-167"><xref:System.Windows.Forms.DataGridView>コントロールには、オブジェクトの動作をカスタマイズするための行関連のイベントとプロパティがいくつかあり <xref:System.Windows.Forms.DataGridViewRow> ます。</span><span class="sxs-lookup"><span data-stu-id="d6122-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="d6122-168">コントロールのプロパティを有効にすると <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 、新しい行を追加するための特殊な行が最後の行として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6122-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="d6122-169">この行はコレクションに含まれてい <xref:System.Windows.Forms.DataGridView.Rows%2A> ますが、注意が必要な特別な機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="d6122-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="d6122-170">詳細については、「 [Windows フォーム DataGridView コントロールでの新しいレコードの行の使用](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6122-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6122-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6122-171">See also</span></span>

- [<span data-ttu-id="d6122-172">DataGridView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="d6122-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="d6122-173">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d6122-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d6122-174">Windows フォーム DataGridView コントロールにおける新規レコード行の使用</span><span class="sxs-lookup"><span data-stu-id="d6122-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
