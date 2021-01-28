---
title: コントロールをドッキングする
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: c765c7e1a109a6185cca130f120d032eb0a6a3cf
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956955"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="cbb6c-102">方法: Windows フォームにコントロールをドッキングする</span><span class="sxs-lookup"><span data-stu-id="cbb6c-102">How to: Dock controls on Windows Forms</span></span>

<span data-ttu-id="cbb6c-103">コントロールをフォームの端にドッキングしたり、コントロールのコンテナー (フォームまたはコンテナーコントロールのいずれか) に入力したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="cbb6c-104">たとえば、Windows エクスプローラーでは、ウィンドウの左側にコントロールがドッキングさ <xref:System.Windows.Forms.TreeView> れ、 <xref:System.Windows.Forms.ListView> コントロールはウィンドウの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="cbb6c-105"><xref:System.Windows.Forms.Control.Dock%2A>ドッキングモードを定義するには、表示されているすべての Windows フォームコントロールに対してプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>

> [!NOTE]
> <span data-ttu-id="cbb6c-106">コントロールは、逆 z オーダーでドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-106">Controls are docked in reverse z-order.</span></span>

<span data-ttu-id="cbb6c-107">プロパティは、 <xref:System.Windows.Forms.Control.Dock%2A> プロパティと対話し <xref:System.Windows.Forms.Control.AutoSize%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="cbb6c-108">詳細については、「[AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="to-dock-a-control"></a><span data-ttu-id="cbb6c-109">コントロールをドッキングするには</span><span class="sxs-lookup"><span data-stu-id="cbb6c-109">To dock a control</span></span>

1. <span data-ttu-id="cbb6c-110">Visual Studio で、ドッキングするコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-110">In Visual Studio, select the control that you want to dock.</span></span>

2. <span data-ttu-id="cbb6c-111">[ **プロパティ** ] ウィンドウで、プロパティの右側にある矢印をクリックし <xref:System.Windows.Forms.Control.Dock%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-111">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

   <span data-ttu-id="cbb6c-112">フォームの端と中央を表す一連のボックスを示すエディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>

3. <span data-ttu-id="cbb6c-113">コントロールをドッキングするフォームの端を表すボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="cbb6c-114">コントロールのフォームまたはコンテナーコントロールの内容を塗りつぶすには、中央のボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="cbb6c-115">[ **(なし)** ] をクリックして、ドッキングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-115">Click **(none)** to disable docking.</span></span>

   <span data-ttu-id="cbb6c-116">ドッキングされた端の境界に合わせてコントロールのサイズが自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cbb6c-117">継承されたコントロールは、ドッキングできる必要があり `Protected` ます。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="cbb6c-118">コントロールのアクセスレベルを変更するには、[**プロパティ**] ウィンドウでその [**修飾子**] プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbb6c-118">To change the access level of a control, set its **Modifier** property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbb6c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbb6c-119">See also</span></span>

- [<span data-ttu-id="cbb6c-120">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="cbb6c-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="cbb6c-121">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="cbb6c-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="cbb6c-122">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="cbb6c-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="cbb6c-123">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="cbb6c-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="cbb6c-124">方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="cbb6c-124">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="cbb6c-125">方法 : TableLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="cbb6c-125">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="cbb6c-126">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="cbb6c-126">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="cbb6c-127">方法 : Windows フォームにコントロールを固定する</span><span class="sxs-lookup"><span data-stu-id="cbb6c-127">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
