---
title: DataGridView コントロールの編集モードを指定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982803"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="59505-102">方法: Windows フォーム DataGridView コントロールの編集モードを指定する</span><span class="sxs-lookup"><span data-stu-id="59505-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="59505-103">既定では、ユーザーは、現在の <xref:System.Windows.Forms.DataGridView> テキストボックスのセルを入力するか、F2 キーを押すことで、その内容を編集できます。</span><span class="sxs-lookup"><span data-stu-id="59505-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="59505-104">これにより、次のすべての条件が満たされた場合にセルが編集モードになります。</span><span class="sxs-lookup"><span data-stu-id="59505-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="59505-105">基になるデータソースは編集をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="59505-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="59505-106"><xref:System.Windows.Forms.DataGridView>コントロールが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="59505-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="59505-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A> プロパティ値が <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically> ではない。</span><span class="sxs-lookup"><span data-stu-id="59505-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="59505-108">`ReadOnly`セル、行、列、およびコントロールのプロパティはすべてに設定されてい `false` ます。</span><span class="sxs-lookup"><span data-stu-id="59505-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="59505-109">編集モードでは、ユーザーはセルの値を変更し、ENTER キーを押して変更をコミットするか、ESC キーを押してセルを元の値に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="59505-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="59505-110"><xref:System.Windows.Forms.DataGridView>セルが現在のセルになるとすぐに編集モードに切り替わるように、コントロールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="59505-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="59505-111">この場合、ENTER キーと ESC キーの動作は変更されませんが、値がコミットまたは元に戻されると、セルは編集モードのままになります。</span><span class="sxs-lookup"><span data-stu-id="59505-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="59505-112">また、ユーザーがセルを入力したとき、またはユーザーが F2 キーを押したときにのみ、セルが編集モードになるように、コントロールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="59505-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="59505-113">最後に、メソッドを呼び出す場合を除き、セルが編集モードに入ってしまうのを防ぐことができます <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 。</span><span class="sxs-lookup"><span data-stu-id="59505-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="59505-114">DataGridView コントロールの編集モードを変更するには</span><span class="sxs-lookup"><span data-stu-id="59505-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="59505-115"><xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>プロパティを適切な列挙値に設定し <xref:System.Windows.Forms.DataGridViewEditMode> ます。</span><span class="sxs-lookup"><span data-stu-id="59505-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="59505-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="59505-116">Compiling the Code</span></span>  
 <span data-ttu-id="59505-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59505-117">This example requires:</span></span>  
  
- <span data-ttu-id="59505-118">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="59505-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="59505-119"><xref:System> アセンブリおよび <xref:System.Windows.Forms> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="59505-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59505-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="59505-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="59505-121">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="59505-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
