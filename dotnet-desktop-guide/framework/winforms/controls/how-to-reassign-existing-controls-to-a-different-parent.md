---
title: '方法: 既存のコントロールを別の親に再配置する'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: 3d31611465eacf471470b90b7829be4a187d771f
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957644"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="b762d-102">方法: 既存のコントロールを別の親に再割り当てする</span><span class="sxs-lookup"><span data-stu-id="b762d-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="b762d-103">フォームに存在するコントロールを新しいコンテナー コントロールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b762d-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="b762d-104">Visual Studio で、 <xref:System.Windows.Forms.Button> **ツールボックス** から3つのコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b762d-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="b762d-105">これらを互いに近づけて配置しますが、整列はさせません。</span><span class="sxs-lookup"><span data-stu-id="b762d-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="b762d-106">**ツールボックス** で <xref:System.Windows.Forms.FlowLayoutPanel> コントロール アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b762d-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="b762d-107">(アイコンをフォームにドラッグしないでください)。</span><span class="sxs-lookup"><span data-stu-id="b762d-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="b762d-108">マウス ポインターを 3 つの <xref:System.Windows.Forms.Button> コントロールに近づけます。</span><span class="sxs-lookup"><span data-stu-id="b762d-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="b762d-109">ポインターが <xref:System.Windows.Forms.FlowLayoutPanel> コントロール アイコンが付いた十字カーソルに変わります。</span><span class="sxs-lookup"><span data-stu-id="b762d-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="b762d-110">マウス ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="b762d-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="b762d-111">マウス ポインターをドラッグして、 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールのアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="b762d-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="b762d-112">3 つの <xref:System.Windows.Forms.Button> コントロールを囲むようにアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="b762d-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="b762d-113">マウスのボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="b762d-113">Release the mouse button.</span></span>

   <span data-ttu-id="b762d-114">これで、3 つの <xref:System.Windows.Forms.Button> コントロールが <xref:System.Windows.Forms.FlowLayoutPanel> コントロールに挿入されました。</span><span class="sxs-lookup"><span data-stu-id="b762d-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="b762d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b762d-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="b762d-116">チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="b762d-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="b762d-117">チュートリアル : スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="b762d-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
