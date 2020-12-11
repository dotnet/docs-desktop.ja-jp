---
title: '方法 : デザイン時にフォームの端に合わせてコントロールを配置する'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982255"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="7ad07-102">方法 : デザイン時にフォームの端に合わせてコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="7ad07-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>

<span data-ttu-id="7ad07-103">プロパティの値を設定することによって、コントロールをフォームの端に合わせることができ <xref:System.Windows.Forms.Control.Dock%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-103">You can make your control align to the edge of your forms by setting the value of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="7ad07-104">このプロパティは、フォーム内のコントロールの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ad07-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="7ad07-105"><xref:System.Windows.Forms.Control.Dock%2A> プロパティには次の値のいずれかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="7ad07-106">設定</span><span class="sxs-lookup"><span data-stu-id="7ad07-106">Setting</span></span>|<span data-ttu-id="7ad07-107">コントロールへの影響</span><span class="sxs-lookup"><span data-stu-id="7ad07-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="7ad07-108">フォームの下部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="7ad07-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="7ad07-109">フォームの残りの全スペースを埋めます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="7ad07-110">フォームの左側にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="7ad07-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="7ad07-111">はどこにもドッキングせず、で指定した場所に表示され <xref:System.Windows.Forms.Control.Location%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="7ad07-112">フォームの右側にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="7ad07-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="7ad07-113">フォームの上部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="7ad07-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="7ad07-114">これらの値は、コードで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-114">These values can also be set in code.</span></span> <span data-ttu-id="7ad07-115">詳細については、「 [方法: フォームの端にコントロールを配置する](how-to-align-a-control-to-the-edges-of-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ad07-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>

## <a name="set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="7ad07-116">デザイン時にコントロールの Dock プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="7ad07-116">Set the Dock property for your control at design time</span></span>

1. <span data-ttu-id="7ad07-117">Visual Studio の Windows フォームデザイナーで、コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ad07-117">In the Windows Forms Designer in Visual Studio, select your control.</span></span>

2. <span data-ttu-id="7ad07-118">[ **プロパティ** ] ウィンドウで、プロパティの横にあるドロップダウンボックスをクリックし <xref:System.Windows.Forms.Control.Dock%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-118">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

     <span data-ttu-id="7ad07-119">6つの設定を表すグラフィカルインターフェイス <xref:System.Windows.Forms.Control.Dock%2A> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ad07-119">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>

3. <span data-ttu-id="7ad07-120">適切な設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ad07-120">Choose the appropriate setting.</span></span>

4. <span data-ttu-id="7ad07-121">これで、設定によって指定された方法でコントロールがドッキングされるようになります。</span><span class="sxs-lookup"><span data-stu-id="7ad07-121">Your control will now dock in the manner specified by the setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ad07-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ad07-122">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7ad07-123">方法: フォームの端に合わせてコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="7ad07-123">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="7ad07-124">チュートリアル : スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="7ad07-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="7ad07-125">方法 : Windows フォームにコントロールを固定する</span><span class="sxs-lookup"><span data-stu-id="7ad07-125">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="7ad07-126">方法 : TableLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="7ad07-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="7ad07-127">方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="7ad07-127">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="7ad07-128">チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="7ad07-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="7ad07-129">チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="7ad07-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="7ad07-130">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="7ad07-130">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
