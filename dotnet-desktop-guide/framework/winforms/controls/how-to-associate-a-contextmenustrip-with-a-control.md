---
title: '方法: ContextMenuStrip をコントロールに関連付ける'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: e1b2a49196d6da66d478a3d44eab64298cebe969
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980964"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="bc552-102">方法: ContextMenuStrip をコントロールに関連付ける</span><span class="sxs-lookup"><span data-stu-id="bc552-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="bc552-103">コントロールとショートカット メニューを作成した後、次の手順を使用することによって、ユーザーがコントロールを右クリックした時点で特定のショートカット メニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="bc552-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="bc552-104">これらの手順は、<xref:System.Windows.Forms.ContextMenuStrip> を Windows フォームと <xref:System.Windows.Forms.ToolStrip> コントロールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="bc552-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="bc552-105">ContextMenuStrip を Windows フォームに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="bc552-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="bc552-106"><xref:System.Windows.Forms.Control.ContextMenuStrip%2A> プロパティを関連付けられている <xref:System.Windows.Forms.ContextMenuStrip> の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="bc552-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="bc552-107">ContextMenuStrip を ToolStrip コントロールに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="bc552-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="bc552-108">コントロールの <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> プロパティを関連付けられている <xref:System.Windows.Forms.ContextMenuStrip> の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="bc552-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc552-109">例</span><span class="sxs-lookup"><span data-stu-id="bc552-109">Example</span></span>  
 <span data-ttu-id="bc552-110">次のコード例では、Windows フォームと <xref:System.Windows.Forms.ToolStrip> を作成して、別の <xref:System.Windows.Forms.ContextMenuStrip> コントロールをそれぞれに関連付けています。</span><span class="sxs-lookup"><span data-stu-id="bc552-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc552-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="bc552-111">Compiling the Code</span></span>  
 <span data-ttu-id="bc552-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bc552-112">This example requires:</span></span>  
  
- <span data-ttu-id="bc552-113">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="bc552-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc552-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc552-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="bc552-115">方法: メニュー項目を ContextMenuStrip に追加する</span><span class="sxs-lookup"><span data-stu-id="bc552-115">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="bc552-116">ContextMenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="bc552-116">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
