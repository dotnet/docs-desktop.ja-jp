---
title: '方法: MDI アプリケーションでメニューの自動マージを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982807"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="9af1e-102">方法: MDI アプリケーションでメニューの自動マージを設定する</span><span class="sxs-lookup"><span data-stu-id="9af1e-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="9af1e-103">次の手順では、マルチドキュメントインターフェイス (MDI) アプリケーションでを使用して自動マージを設定するための基本的な手順を示し <xref:System.Windows.Forms.MenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="9af1e-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="9af1e-104">メニューの自動マージを設定するには</span><span class="sxs-lookup"><span data-stu-id="9af1e-104">To set up automatic menu merging</span></span>  
  
1. <span data-ttu-id="9af1e-105">MDI 親フォームを作成するには、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="9af1e-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="9af1e-106">を <xref:System.Windows.Forms.MenuStrip> MDI 親に追加し、その <xref:System.Windows.Forms.Form.MainMenuStrip%2A> プロパティをそれに設定 <xref:System.Windows.Forms.MenuStrip> します。</span><span class="sxs-lookup"><span data-stu-id="9af1e-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3. <span data-ttu-id="9af1e-107">MDI 子フォームを作成し、その <xref:System.Windows.Forms.Form.MdiParent%2A> プロパティを親フォームの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="9af1e-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4. <span data-ttu-id="9af1e-108">を <xref:System.Windows.Forms.MenuStrip> MDI 子フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="9af1e-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5. <span data-ttu-id="9af1e-109">子フォームで、 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> のプロパティ <xref:System.Windows.Forms.MenuStrip> をに設定 `false` します。</span><span class="sxs-lookup"><span data-stu-id="9af1e-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6. <span data-ttu-id="9af1e-110"><xref:System.Windows.Forms.MenuStrip>子フォームがアクティブになったときに親フォームにマージする子フォームに、メニュー項目を追加し <xref:System.Windows.Forms.MenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="9af1e-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7. <span data-ttu-id="9af1e-111"><xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>子フォームのメニュー項目のプロパティを使用して、 <xref:System.Windows.Forms.MenuStrip> 親フォームへのマージ方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="9af1e-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af1e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9af1e-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="9af1e-113">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9af1e-113">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
