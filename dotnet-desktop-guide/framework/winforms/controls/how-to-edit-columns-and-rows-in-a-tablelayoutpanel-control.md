---
title: '方法: TableLayoutPanel コントロールの列と行を編集する'
description: '[列と行のスタイル] ダイアログボックスを使用して、Windows フォームコントロールの行と列を編集する方法について説明します。'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: cfd2ca4be5d5a2658a9a129d911f1dba9670ccfd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982523"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="5e7b7-103">方法: TableLayoutPanel コントロールの列と行を編集する</span><span class="sxs-lookup"><span data-stu-id="5e7b7-103">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="5e7b7-104">[ <xref:System.Windows.Forms.TableLayoutPanel> **列と行のスタイル** ] ダイアログボックスと呼ばれるコントロールのコレクションエディターを使用して、コントロールの行と列を編集できます。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-104">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="5e7b7-105">コントロールが複数の行または列にまたがるようにするには、 `RowSpan` コントロールのプロパティとプロパティを設定し `ColumnSpan` ます。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-105">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="5e7b7-106">詳細については、「 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-106">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="5e7b7-107">セル内にコントロールを配置する場合、またはコントロールをセル内に引き伸ばす場合は、コントロールのプロパティを使用し <xref:System.Windows.Forms.Control.Anchor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-107">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="5e7b7-108">詳細については、「 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="5e7b7-109">行と列を編集するには</span><span class="sxs-lookup"><span data-stu-id="5e7b7-109">To edit rows and columns</span></span>

1. <span data-ttu-id="5e7b7-110"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-110">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="5e7b7-111"><xref:System.Windows.Forms.TableLayoutPanel>コントロールのデザイナーの [アクション] グリフ ( ![ 小さい黒い矢印) をクリック ](./media/designer-actions-glyph.gif) し、[**行と列の編集**] を選択して [**列と行のスタイル**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-111">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="5e7b7-112">また、コントロールを右クリック <xref:System.Windows.Forms.TableLayoutPanel> し、ショートカットメニューの [ **行と列の編集** ] をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-112">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="5e7b7-113">列を追加または削除するには、[**メンバーの種類**] ボックスの一覧から **列** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-113">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="5e7b7-114">行を追加または削除するには、[**メンバーの種類**] ボックスの一覧から [**行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-114">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="5e7b7-115">**メンバー** リストの末尾に行または列を追加するには、[**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-115">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="5e7b7-116">一覧で現在選択されている項目の前に行または列を追加するには、[ **挿入** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-116">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="5e7b7-117">行または列を追加する場合は、新しい行または列の **サイズの種類** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-117">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="5e7b7-118">詳細については、「<xref:System.Windows.Forms.SizeType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-118">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="5e7b7-119">行または列を削除するには、[ **削除** ] ボタンをクリックして、 **メンバー** リストで現在選択されているアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e7b7-119">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e7b7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e7b7-120">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="5e7b7-121">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="5e7b7-121">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
