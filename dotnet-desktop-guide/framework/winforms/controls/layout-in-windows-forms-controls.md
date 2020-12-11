---
title: コントロールのレイアウト
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: ed8603e997e7d0c1ed7a2ebda6dc960726d32f45
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980647"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="c0fb3-102">Windows フォーム コントロールのレイアウト</span><span class="sxs-lookup"><span data-stu-id="c0fb3-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="c0fb3-103">フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="c0fb3-104">名前空間には、 <xref:System.Windows.Forms?displayProperty=nameWithType> これを実現するための多数のレイアウトツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c0fb3-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c0fb3-105">In This Section</span></span>

<span data-ttu-id="c0fb3-106">[AutoSize プロパティの概要](autosize-property-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c0fb3-106">[AutoSize Property Overview](autosize-property-overview.md)</span></span>\
<span data-ttu-id="c0fb3-107"><xref:System.Windows.Forms.Control.AutoSize%2A>レイアウトにおけるプロパティとそのロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="c0fb3-108">[Windows フォームコントロールの余白と埋め込み](margin-and-padding-in-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="c0fb3-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)</span></span>\
<span data-ttu-id="c0fb3-109">およびの <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Padding%2A> 各プロパティとそのロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="c0fb3-110">[方法: フォームの端にコントロールを配置する](how-to-align-a-control-to-the-edges-of-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c0fb3-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)</span></span>\
<span data-ttu-id="c0fb3-111">プロパティを使用し <xref:System.Windows.Forms.Control.Dock%2A> て、コントロールをフォームの端に揃える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="c0fb3-112">[方法: 埋め込みを使用して Windows フォームコントロールの周囲に境界線を作成する](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span><span class="sxs-lookup"><span data-stu-id="c0fb3-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span></span>\
<span data-ttu-id="c0fb3-113">プロパティを使用して、コントロールのアウトラインを指定する方法を示し <xref:System.Windows.Forms.Control.Padding%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="c0fb3-114">[方法: カスタムレイアウトエンジンを実装する](how-to-implement-a-custom-layout-engine.md)</span><span class="sxs-lookup"><span data-stu-id="c0fb3-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)</span></span>\
<span data-ttu-id="c0fb3-115">Windows フォームコントロールを配置するためのを実装する方法を示し <xref:System.Windows.Forms.Layout.LayoutEngine> ます。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="c0fb3-116">リファレンス</span><span class="sxs-lookup"><span data-stu-id="c0fb3-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="c0fb3-117"><xref:System.Windows.Forms.TableLayoutPanel> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="c0fb3-118"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0fb3-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0fb3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0fb3-119">See also</span></span>

- [<span data-ttu-id="c0fb3-120">方法: FlowLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="c0fb3-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="c0fb3-121">方法 : TableLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="c0fb3-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="c0fb3-122">方法 : ローカリゼーションに対応した Windows フォーム レイアウトをデザインする</span><span class="sxs-lookup"><span data-stu-id="c0fb3-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="c0fb3-123">TableLayoutPanel コントロールにおける AutoSize 動作</span><span class="sxs-lookup"><span data-stu-id="c0fb3-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
