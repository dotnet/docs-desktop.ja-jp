---
title: StatusBar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983731"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="a5721-102">StatusBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="a5721-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a5721-103">コントロールとコントロールは、およびコントロール <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> に対して、機能の置き換えと追加を行います。ただし、コントロール <xref:System.Windows.Forms.StatusBar> とコントロールは、 <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 下位互換性と将来の使用の両方について、選択した場合に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a5721-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a5721-104">Windows フォーム [StatusBar コントロール](statusbar-control-windows-forms.md) は、フォーム上で通常はウィンドウの下部に表示される領域として使用されます。この領域では、アプリケーションはさまざまな種類の状態情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a5721-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="a5721-105"><xref:System.Windows.Forms.StatusBar> コントロールには、状態を示すためにテキストまたはアイコンを表示するステータスバーパネル、またはプロセスが動作していることを示すアニメーション内の一連のアイコンがあります。たとえば、Microsoft Word では、ドキュメントが保存されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a5721-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="a5721-106">StatusBar コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="a5721-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="a5721-107">Internet Explorer は、ハイパーリンク上でマウスがロールオーバーしたときに、ステータスバーを使用してページの URL を示します。Microsoft Word では、ページの場所、セクションの場所、および上書きやリビジョンの追跡などの編集モードに関する情報が提供されます。また、Visual Studio はステータスバーを使用して、ドッキングされたウィンドウをドッキングまたはフローティングとして操作する方法を示すなど、状況に応じた情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5721-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="a5721-108">ステータスバーに1つのメッセージを表示するには、 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> プロパティを `false` (既定値) に設定し、ステータスバー <xref:System.Windows.Forms.StatusBar.Text%2A> のプロパティをステータスバーに表示するテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="a5721-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="a5721-109">ステータスバーをパネルに分割して複数の種類の情報を表示するには、プロパティをに設定し、 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> `true` のメソッドを使用し <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="a5721-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5721-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5721-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="a5721-111">方法: Windows フォームの StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="a5721-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
