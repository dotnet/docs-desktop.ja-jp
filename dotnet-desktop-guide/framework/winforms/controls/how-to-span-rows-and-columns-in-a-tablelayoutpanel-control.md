---
title: '方法: TableLayoutPanel コントロールの行と列を拡大する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983008"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="0f5d5-102">方法: TableLayoutPanel コントロールの行と列を拡大する</span><span class="sxs-lookup"><span data-stu-id="0f5d5-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="0f5d5-103">コントロール内のコントロール <xref:System.Windows.Forms.TableLayoutPanel> は、隣接する行と列にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="0f5d5-104">列と行をスパンするには</span><span class="sxs-lookup"><span data-stu-id="0f5d5-104">To span columns and rows</span></span>

1. <span data-ttu-id="0f5d5-105"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="0f5d5-106">[ツールボックス] からコントロールをドラッグして、 <xref:System.Windows.Forms.Button> コントロールの左上のセルに移動し <xref:System.Windows.Forms.TableLayoutPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="0f5d5-107"><xref:System.Windows.Forms.Button>コントロールの **columnspan** プロパティを **2** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="0f5d5-108">コントロールが1番目 <xref:System.Windows.Forms.Button> と2番目の列にまたがっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="0f5d5-109"><xref:System.Windows.Forms.Button>コントロールの **RowSpan** プロパティを **2** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="0f5d5-110"><xref:System.Windows.Forms.Button>コントロールが1行目と2番目の行にまたがっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="0f5d5-111"><xref:System.Windows.Forms.Button>コントロールの **columnspan** プロパティを **1** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="0f5d5-112"><xref:System.Windows.Forms.Button>コントロールが最初の列に移動し、最初の行と2番目の行にまたがっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0f5d5-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f5d5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f5d5-113">See also</span></span>

- [<span data-ttu-id="0f5d5-114">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="0f5d5-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
