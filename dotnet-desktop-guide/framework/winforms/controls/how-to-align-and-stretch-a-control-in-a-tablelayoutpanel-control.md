---
title: '方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982252"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="6beec-102">方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する</span><span class="sxs-lookup"><span data-stu-id="6beec-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="6beec-103">との各プロパティを使用して、コントロールの配置と伸縮を行うことができ <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.Control.Anchor%2A> <xref:System.Windows.Forms.Control.Dock%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="6beec-104">コントロールを配置して伸縮する</span><span class="sxs-lookup"><span data-stu-id="6beec-104">Align and stretch a control</span></span>

1. <span data-ttu-id="6beec-105">Visual Studio で、 <xref:System.Windows.Forms.TableLayoutPanel> **ツールボックス** からコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6beec-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="6beec-106">[ツールボックス] からコントロールをドラッグして、 <xref:System.Windows.Forms.Button> コントロールの左上のセルに移動し <xref:System.Windows.Forms.TableLayoutPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="6beec-107"><xref:System.Windows.Forms.Button>コントロールがセルの中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="6beec-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="6beec-108"><xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し `Left,Right` ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="6beec-109">コントロールは、 <xref:System.Windows.Forms.Button> セルの幅に合わせて拡大されます。</span><span class="sxs-lookup"><span data-stu-id="6beec-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="6beec-110"><xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し `Top,Bottom` ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="6beec-111">コントロールは、 <xref:System.Windows.Forms.Button> セルの高さに合わせて拡大されます。</span><span class="sxs-lookup"><span data-stu-id="6beec-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="6beec-112"><xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Dock%2A> をに設定し <xref:System.Windows.Forms.DockStyle.Fill> ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="6beec-113"><xref:System.Windows.Forms.Button>コントロールがセルに合わせて拡大されます。</span><span class="sxs-lookup"><span data-stu-id="6beec-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="6beec-114"><xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Dock%2A> をに設定し <xref:System.Windows.Forms.DockStyle.None> ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="6beec-115"><xref:System.Windows.Forms.Button>コントロールは元のサイズに戻り、セルの左上隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="6beec-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="6beec-116">**Windows フォームデザイナー** によってプロパティがに設定されてい <xref:System.Windows.Forms.Control.Anchor%2A> `Top, Left` ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="6beec-117"><xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し `Bottom,Right` ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="6beec-118"><xref:System.Windows.Forms.Button>コントロールがセルの右下隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="6beec-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="6beec-119"><xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Anchor%2A> をに設定し <xref:System.Windows.Forms.AnchorStyles.None> ます。</span><span class="sxs-lookup"><span data-stu-id="6beec-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="6beec-120"><xref:System.Windows.Forms.Button>コントロールがセルの中央に移動します。</span><span class="sxs-lookup"><span data-stu-id="6beec-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="6beec-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6beec-121">See also</span></span>

- [<span data-ttu-id="6beec-122">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="6beec-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
