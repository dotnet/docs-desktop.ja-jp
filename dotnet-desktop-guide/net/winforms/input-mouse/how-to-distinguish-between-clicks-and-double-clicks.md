---
title: クリックとダブルクリックを区別する方法
description: .NET 用 Windows フォームのコントロールまたはフォームを使用してクリックとダブルクリックの違いを検出するさまざまな方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.openlocfilehash: 7b58896a85ffd16ae2637b94d58845ed7a721c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942174"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks-windows-forms-net"></a><span data-ttu-id="c1d42-103">クリックとダブルクリックを区別する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="c1d42-103">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>

<span data-ttu-id="c1d42-104">通常、1 回の "*クリック*" によってユーザー インターフェイスのアクションが開始され、"*ダブルクリック*" によってそのアクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="c1d42-104">Typically, a single *click* initiates a user interface action and a *double-click* extends the action.</span></span> <span data-ttu-id="c1d42-105">たとえば、通常、1 回のクリックで項目が選択され、ダブルクリックでその項目が編集されます。</span><span class="sxs-lookup"><span data-stu-id="c1d42-105">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="c1d42-106">ただし、Windows フォームのクリック イベントでは、クリックとダブルクリックによって矛盾するアクションが実行されるようなシナリオには簡単に対応できません。それは、<xref:System.Windows.Forms.Control.Click> イベントや <xref:System.Windows.Forms.Control.MouseClick> イベントに結び付けられたアクションが、<xref:System.Windows.Forms.Control.DoubleClick> イベントや <xref:System.Windows.Forms.Control.MouseDoubleClick> イベントに結び付けられたアクションの前に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="c1d42-106">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="c1d42-107">ここでは、この問題の 2 つの解決方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-107">This topic demonstrates two solutions to this problem.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="c1d42-108">1 つの解決方法は、ダブルクリック イベントを処理し、クリック イベントの処理のアクションをロールバックすることです。</span><span class="sxs-lookup"><span data-stu-id="c1d42-108">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="c1d42-109">まれに、クリック動作およびダブルクリック動作のシミュレートが必要になることがあります。その場合は、<xref:System.Windows.Forms.Control.MouseDown> イベントを処理し、<xref:System.Windows.Forms.SystemInformation> クラスの <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> プロパティと <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-109">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="c1d42-110">クリック間の時間を測定し、<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> の値に到達する前に 2 回目のクリックが発生しており、かつ <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> によって定義された四角形内でクリックが行われている場合は、ダブルクリック アクションが実行されます。それ以外の場合は、クリック アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1d42-110">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>

## <a name="to-roll-back-a-click-action"></a><span data-ttu-id="c1d42-111">クリック アクションをロールバックするには</span><span class="sxs-lookup"><span data-stu-id="c1d42-111">To roll back a click action</span></span>

<span data-ttu-id="c1d42-112">対象のコントロールに標準のダブルクリック動作が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-112">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="c1d42-113">含まれない場合は、<xref:System.Windows.Forms.Control.SetStyle%2A> メソッドを使用してコントロールでダブルクリックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1d42-113">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="c1d42-114">ダブルクリック イベントを処理して、ダブルクリック アクションを実行するだけでなく、クリック アクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="c1d42-114">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="c1d42-115">ダブルクリックが有効になっているカスタム ボタンを作成する方法と、ダブルクリック イベント処理コード内でクリック アクションをロールバックする方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-115">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>

<span data-ttu-id="c1d42-116">このコード例では、ダブルクリックを有効にする新しいボタン コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c1d42-116">This code example uses a new button control that enables double-clicks:</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/DoubleClickButton.cs" id="DoubleClickButton":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/DoubleClickButton.vb" id="DoubleClickButton":::

<span data-ttu-id="c1d42-117">次のコードは、新しいボタン コントロールのクリックまたはダブルクリックに基づいて、フォームの境界線のスタイルを変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c1d42-117">The following code demonstrates how a form changes the style of border based on a click or double-click of the new button control:</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form1.cs" id="RollbackForm":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form1.vb" id="RollbackForm":::

## <a name="to-distinguish-between-clicks"></a><span data-ttu-id="c1d42-118">クリックを区別するには</span><span class="sxs-lookup"><span data-stu-id="c1d42-118">To distinguish between clicks</span></span>

<span data-ttu-id="c1d42-119"><xref:System.Windows.Forms.Control.MouseDown> イベントを処理し、<xref:System.Windows.Forms.SystemInformation> プロパティと <xref:System.Windows.Forms.Timer> コンポーネントを使用して、クリックが発生した場所および間隔を確認します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-119">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the <xref:System.Windows.Forms.SystemInformation> property and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="c1d42-120">クリックとダブルクリックのどちらが発生したかに応じて、適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-120">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="c1d42-121">これを実行する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="c1d42-121">The following code example demonstrates how this can be done.</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form2.cs":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form2.vb":::

## <a name="see-also"></a><span data-ttu-id="c1d42-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1d42-122">See also</span></span>

- [<span data-ttu-id="c1d42-123">マウスの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="c1d42-123">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="c1d42-124">マウス イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="c1d42-124">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="c1d42-125">マウス ポインターを管理する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="c1d42-125">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
- [<span data-ttu-id="c1d42-126">マウス イベントをシミュレートする方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="c1d42-126">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control.Click?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.MouseDown?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.SetStyle%2A?displayProperty=nameWithType>
