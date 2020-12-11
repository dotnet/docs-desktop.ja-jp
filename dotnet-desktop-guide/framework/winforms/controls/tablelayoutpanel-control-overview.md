---
title: TableLayoutPanel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: 65daba0ce1a6f1c37fb257c1029396577821aad9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980041"
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="35ab9-102">TableLayoutPanel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="35ab9-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="35ab9-103"><xref:System.Windows.Forms.TableLayoutPanel> コントロールは、その内容をグリッド内に配置します。</span><span class="sxs-lookup"><span data-stu-id="35ab9-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="35ab9-104">レイアウトはデザイン時と実行時の両方で行われるため、アプリケーション環境の変更に合わせて動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="35ab9-105">これにより、パネル内のコントロールを適切にサイズ変更することができるため、親コントロールのサイズ変更や、ローカライズによるテキスト長の変更などの変更に対応できます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="35ab9-106">Windows フォーム コントロールは、<xref:System.Windows.Forms.TableLayoutPanel> の他のインスタンスを含めて、<xref:System.Windows.Forms.TableLayoutPanel> コントロールの子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="35ab9-107">これにより、実行時の変化に適応する高度なレイアウトを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="35ab9-108"><xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>、<xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>、および <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> プロパティの値に応じて、<xref:System.Windows.Forms.TableLayoutPanel> コントロールを追加するときに新しいコントロールに合わせて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="35ab9-109"><xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> プロパティまたは <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> プロパティのいずれかを 0 の値に設定すると、<xref:System.Windows.Forms.TableLayoutPanel> が対応する方向にバインド解除されます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="35ab9-110"><xref:System.Windows.Forms.TableLayoutPanel> コントロールが完全に子コントロールになった後で、(水平または垂直の) 展開の方向を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="35ab9-111">既定では、<xref:System.Windows.Forms.TableLayoutPanel> コントロールは行を追加することで下方向に拡張します。</span><span class="sxs-lookup"><span data-stu-id="35ab9-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="35ab9-112">既定の動作とは異なる方法で行と列を動作させる場合は、<xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> プロパティと <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> プロパティを使用して、行と列のプロパティを制御できます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="35ab9-113">行または列のプロパティを個別に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="35ab9-114"><xref:System.Windows.Forms.TableLayoutPanel> コントロールは、その子コントロールに `Cell`、`Column`、`Row`、`ColumnSpan`、および `RowSpan` の各プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="35ab9-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="35ab9-115">子コントロールで `ColumnSpan` プロパティまたは `RowSpan` プロパティを設定することで、<xref:System.Windows.Forms.TableLayoutPanel> コントロールのセルをマージできます。</span><span class="sxs-lookup"><span data-stu-id="35ab9-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1. [<span data-ttu-id="35ab9-116">方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する</span><span class="sxs-lookup"><span data-stu-id="35ab9-116">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="35ab9-117">方法: TableLayoutPanel コントロールの行と列を拡大する</span><span class="sxs-lookup"><span data-stu-id="35ab9-117">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="35ab9-118">方法: TableLayoutPanel コントロールの列と行を編集する</span><span class="sxs-lookup"><span data-stu-id="35ab9-118">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="35ab9-119">チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="35ab9-119">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="see-also"></a><span data-ttu-id="35ab9-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="35ab9-120">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutSettings>
- [<span data-ttu-id="35ab9-121">方法 : ローカリゼーションに対応した Windows フォーム レイアウトをデザインする</span><span class="sxs-lookup"><span data-stu-id="35ab9-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="35ab9-122">方法 : データ入力用のサイズ変更可能な Windows フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="35ab9-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)
- [<span data-ttu-id="35ab9-123">TableLayoutPanel コントロールの推奨される手順</span><span class="sxs-lookup"><span data-stu-id="35ab9-123">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)
