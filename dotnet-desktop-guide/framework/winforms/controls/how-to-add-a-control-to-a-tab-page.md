---
title: '方法: タブ ページにコントロールを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 9806583fda60f1cb8a5ef2d97f42eba158593f61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981020"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="6198c-102">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="6198c-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="6198c-103">Windows フォームを使用すると、 <xref:System.Windows.Forms.TabControl> 他のコントロールを整理して表示できます。</span><span class="sxs-lookup"><span data-stu-id="6198c-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="6198c-104">次の手順は、最初のタブにボタンを追加する方法を示しています。タブページのラベル部分にアイコンを追加する方法の詳細については、「 [方法: Windows フォーム TabControl の外観を変更する](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6198c-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="6198c-105">プログラムによってコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="6198c-105">To add a control programmatically</span></span>  
  
1. <span data-ttu-id="6198c-106"><xref:System.Windows.Forms.Control.ControlCollection.Add%2A>のプロパティによって返されるコレクションのメソッドを使用し <xref:System.Windows.Forms.Control.Controls%2A> <xref:System.Windows.Forms.TabPage> ます。</span><span class="sxs-lookup"><span data-stu-id="6198c-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6198c-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="6198c-107">See also</span></span>

- [<span data-ttu-id="6198c-108">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="6198c-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="6198c-109">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6198c-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="6198c-110">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="6198c-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="6198c-111">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="6198c-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="6198c-112">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="6198c-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
