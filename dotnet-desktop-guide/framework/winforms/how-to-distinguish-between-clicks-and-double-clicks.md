---
title: '方法: クリックとダブルクリックを識別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
ms.openlocfilehash: cff6c283651b5994e869756524a3ee83ecdcfda9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974343"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a><span data-ttu-id="7922b-102">方法: クリックとダブルクリックを識別する</span><span class="sxs-lookup"><span data-stu-id="7922b-102">How to: Distinguish Between Clicks and Double-Clicks</span></span>
<span data-ttu-id="7922b-103">通常、1 回の *クリック* によってユーザー インターフェイス (UI) のアクションが開始され、*ダブルクリック* によってそのアクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="7922b-103">Typically, a single *click* initiates a user interface (UI) action and a *double-click* extends the action.</span></span> <span data-ttu-id="7922b-104">たとえば、通常、1 回のクリックで項目が選択され、ダブルクリックでその項目が編集されます。</span><span class="sxs-lookup"><span data-stu-id="7922b-104">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="7922b-105">ただし、Windows フォームのクリック イベントでは、クリックとダブルクリックによって矛盾するアクションが実行されるようなシナリオには簡単に対応できません。それは、<xref:System.Windows.Forms.Control.Click> イベントや <xref:System.Windows.Forms.Control.MouseClick> イベントに結び付けられたアクションが、<xref:System.Windows.Forms.Control.DoubleClick> イベントや <xref:System.Windows.Forms.Control.MouseDoubleClick> イベントに結び付けられたアクションの前に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="7922b-105">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="7922b-106">ここでは、この問題の 2 つの解決方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7922b-106">This topic demonstrates two solutions to this problem.</span></span> <span data-ttu-id="7922b-107">1 つの解決方法は、ダブルクリック イベントを処理し、クリック イベントの処理のアクションをロールバックすることです。</span><span class="sxs-lookup"><span data-stu-id="7922b-107">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="7922b-108">まれに、クリック動作およびダブルクリック動作のシミュレートが必要になることがあります。その場合は、<xref:System.Windows.Forms.Control.MouseDown> イベントを処理し、<xref:System.Windows.Forms.SystemInformation> クラスの <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> プロパティと <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="7922b-108">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="7922b-109">クリック間の時間を測定し、<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> の値に到達する前に 2 回目のクリックが発生しており、かつ <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> によって定義された四角形内でクリックが行われている場合は、ダブルクリック アクションが実行されます。それ以外の場合は、クリック アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7922b-109">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>  
  
### <a name="to-roll-back-a-click-action"></a><span data-ttu-id="7922b-110">クリック アクションをロールバックするには</span><span class="sxs-lookup"><span data-stu-id="7922b-110">To roll back a click action</span></span>  
  
- <span data-ttu-id="7922b-111">対象のコントロールに標準のダブルクリック動作が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7922b-111">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="7922b-112">含まれない場合は、<xref:System.Windows.Forms.Control.SetStyle%2A> メソッドを使用してコントロールでダブルクリックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7922b-112">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="7922b-113">ダブルクリック イベントを処理して、ダブルクリック アクションを実行するだけでなく、クリック アクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="7922b-113">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="7922b-114">ダブルクリックが有効になっているカスタム ボタンを作成する方法と、ダブルクリック イベント処理コード内でクリック アクションをロールバックする方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="7922b-114">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a><span data-ttu-id="7922b-115">MouseDown イベントでのクリックを区別するには</span><span class="sxs-lookup"><span data-stu-id="7922b-115">To distinguish between clicks in the MouseDown event</span></span>  
  
- <span data-ttu-id="7922b-116"><xref:System.Windows.Forms.Control.MouseDown> イベントを処理し、適切な <xref:System.Windows.Forms.SystemInformation> プロパティと <xref:System.Windows.Forms.Timer> コンポーネントを使用して、クリックが発生した場所および間隔を確認します。</span><span class="sxs-lookup"><span data-stu-id="7922b-116">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the appropriate <xref:System.Windows.Forms.SystemInformation> properties and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="7922b-117">クリックとダブルクリックのどちらが発生したかに応じて、適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7922b-117">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="7922b-118">これを実行する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="7922b-118">The following code example demonstrates how this can be done.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7922b-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7922b-119">Compiling the Code</span></span>  
 <span data-ttu-id="7922b-120">これらの例には以下のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="7922b-120">These examples require:</span></span>  
  
- <span data-ttu-id="7922b-121">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7922b-121">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7922b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7922b-122">See also</span></span>

- [<span data-ttu-id="7922b-123">Windows フォーム アプリケーションにおけるマウス入力</span><span class="sxs-lookup"><span data-stu-id="7922b-123">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
