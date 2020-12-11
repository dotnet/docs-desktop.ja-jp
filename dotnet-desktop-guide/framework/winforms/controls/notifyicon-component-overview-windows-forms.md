---
title: NotifyIcon コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 587bf514db853f1122ed16abc05a195985c5ce8d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982920"
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="c789c-102">NotifyIcon コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="c789c-102">NotifyIcon Component Overview (Windows Forms)</span></span>

<span data-ttu-id="c789c-103">Windows フォームの <xref:System.Windows.Forms.NotifyIcon> コンポーネントは、通常、バックグラウンドで動作し、ユーザー インターフェイスに長時間表示されないプロセスのアイコンを表示する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c789c-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="c789c-104">たとえば、タスクバーの状態通知領域のアイコンをクリックしてアクセス可能なウイルス対策プログラムなどです。</span><span class="sxs-lookup"><span data-stu-id="c789c-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>

## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="c789c-105">NotifyIcons のキー プロパティ</span><span class="sxs-lookup"><span data-stu-id="c789c-105">Key Properties of NotifyIcons</span></span>

<span data-ttu-id="c789c-106">各 <xref:System.Windows.Forms.NotifyIcon> コンポーネントは、ステータス領域に 1 つのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="c789c-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="c789c-107">3 つのバック グラウンド プロセスがあり、それぞれのアイコンを表示する必要がある場合は、3 つの <xref:System.Windows.Forms.NotifyIcon> コンポーネントをフォームに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c789c-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="c789c-108"><xref:System.Windows.Forms.NotifyIcon> コンポーネントのキー プロパティは、<xref:System.Windows.Forms.NotifyIcon.Icon%2A> および <xref:System.Windows.Forms.NotifyIcon.Visible%2A> です。</span><span class="sxs-lookup"><span data-stu-id="c789c-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="c789c-109"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> プロパティは、ステータス領域に表示されるアイコンを設定します。</span><span class="sxs-lookup"><span data-stu-id="c789c-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="c789c-110">アイコンを表示するために、<xref:System.Windows.Forms.NotifyIcon.Visible%2A> プロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c789c-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>

## <a name="notifyicons-options"></a><span data-ttu-id="c789c-111">NotifyIcons オプション</span><span class="sxs-lookup"><span data-stu-id="c789c-111">NotifyIcons Options</span></span>

<span data-ttu-id="c789c-112">バルーン ヒント、ショートカット メニュー、およびツールヒントを <xref:System.Windows.Forms.NotifyIcon> に関連付けて、ユーザーを支援できます。</span><span class="sxs-lookup"><span data-stu-id="c789c-112">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>

<span data-ttu-id="c789c-113"><xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> メソッドを呼び出して、バルーンヒントを表示する期間を指定することで、<xref:System.Windows.Forms.NotifyIcon> のバルーン ヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c789c-113">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="c789c-114">テキスト、アイコン、およびとバルーン ヒントのタイトルを、それぞれ <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>、<xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A>、および <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A> を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="c789c-114">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="c789c-115"><xref:System.Windows.Forms.NotifyIcon> コンポーネントには、ツールヒントとショートカット メニューも関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c789c-115"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="c789c-116">詳細については、「 [ToolTip コンポーネントの概要](tooltip-component-overview-windows-forms.md) 」および「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c789c-116">For more information, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c789c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c789c-117">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- [<span data-ttu-id="c789c-118">NotifyIcon コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c789c-118">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
