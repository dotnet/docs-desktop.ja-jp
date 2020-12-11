---
title: HScrollBar コントロールと VScrollBar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982995"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="2bc8d-102">HScrollBar コントロールと VScrollBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="2bc8d-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="2bc8d-103">Windows フォームコントロールを使用して、 <xref:System.Windows.Forms.ScrollBar> アプリケーションまたはコントロール内で水平方向または垂直方向にスクロールすることにより、項目の長い一覧または大量の情報を簡単に移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="2bc8d-104">スクロールバーは、Windows インターフェイスの共通要素であるため、 <xref:System.Windows.Forms.ScrollBar> 多くの場合、コントロールはクラスから派生しないコントロールで使用され <xref:System.Windows.Forms.ScrollableControl> ます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="2bc8d-105">同様に、多くの開発者は、 <xref:System.Windows.Forms.ScrollBar> 独自のユーザーコントロールを作成するときにコントロールを組み込むことを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="2bc8d-106"><xref:System.Windows.Forms.HScrollBar>(水平) コントロールと <xref:System.Windows.Forms.VScrollBar> (垂直) コントロールは、他のコントロールとは独立して動作し、独自のイベント、プロパティ、およびメソッドのセットを持ちます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="2bc8d-107"><xref:System.Windows.Forms.ScrollBar> コントロールは、テキストボックス、リストボックス、コンボボックス、または MDI フォームに関連付けられている組み込みのスクロールバーと同じではありません (コントロールには、 <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.TextBox.ScrollBars%2A> コントロールに関連付けられているスクロールバーを表示または非表示にするプロパティがあります)。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="2bc8d-108">コントロールは、スクロール <xref:System.Windows.Forms.ScrollBar> <xref:System.Windows.Forms.ScrollBar.Scroll> バーに沿ったスクロールボックス (つまみとも呼ばれます) の動きを監視するために、イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="2bc8d-109">イベントを使用 <xref:System.Windows.Forms.ScrollBar.Scroll> すると、スクロールバーの値をドラッグしているときの値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="2bc8d-110">Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="2bc8d-110">Value Property</span></span>  
 <span data-ttu-id="2bc8d-111"><xref:System.Windows.Forms.ScrollBar.Value%2A>プロパティ (既定では 0) は、 `integer` スクロールバーのスクロールボックスの位置に対応する値です。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="2bc8d-112">スクロールボックスの位置が最小値になると、左端 (水平スクロールバーの場合) または一番上の位置 (垂直スクロールバーの場合) に移動します。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="2bc8d-113">スクロールボックスが最大値になると、スクロールボックスが右端または下の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="2bc8d-114">同様に、範囲の下端と上端の中間にある値によって、スクロールボックスの先頭端がスクロールバーの中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="2bc8d-115">ユーザーは、マウスクリックを使用してスクロールバーの値を変更するだけでなく、スクロールボックスをバー上の任意のポイントにドラッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="2bc8d-116">結果の値は、スクロールボックスの位置によって異なりますが、常に <xref:System.Windows.Forms.ScrollBar.Minimum%2A> ユーザーが設定する to プロパティの範囲内にあり <xref:System.Windows.Forms.ScrollBar.Maximum%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="2bc8d-117">Largechange] プロパティと Smallchange] プロパティ</span><span class="sxs-lookup"><span data-stu-id="2bc8d-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="2bc8d-118">ユーザーが pageup キーまたは pagedown キーを押すか、スクロールボックスの両側のスクロールバートラックをクリックすると、プロパティ <xref:System.Windows.Forms.ScrollBar.Value%2A> に設定されている値に従ってプロパティが変更され <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="2bc8d-119">ユーザーがいずれかの方向キーを押すか、スクロールバーのボタンのいずれかをクリックすると、プロパティ <xref:System.Windows.Forms.ScrollBar.Value%2A> に設定されている値に従ってプロパティが変更され <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2bc8d-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc8d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bc8d-120">See also</span></span>

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [<span data-ttu-id="2bc8d-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="2bc8d-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
