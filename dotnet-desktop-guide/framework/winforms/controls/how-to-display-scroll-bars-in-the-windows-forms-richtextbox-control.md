---
title: RichTextBox コントロールにスクロールバーを表示する
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982551"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="99e8a-102">方法: Windows フォームの RichTextBox コントロールにスクロール バーを表示する</span><span class="sxs-lookup"><span data-stu-id="99e8a-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="99e8a-103">既定では、Windows フォームコントロールには、 <xref:System.Windows.Forms.RichTextBox> 必要に応じて水平スクロールバーと垂直スクロールバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="99e8a-104">次の表に示すように、コントロールのプロパティに使用できる値は7つあり <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> <xref:System.Windows.Forms.RichTextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="99e8a-105">RichTextBox コントロールにスクロールバーを表示するには</span><span class="sxs-lookup"><span data-stu-id="99e8a-105">To display scroll bars in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="99e8a-106"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="99e8a-107"><xref:System.Windows.Forms.RichTextBox.Multiline%2A>プロパティがに設定されている場合、水平を含むスクロールバーの種類は表示されません `false` 。</span><span class="sxs-lookup"><span data-stu-id="99e8a-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2. <span data-ttu-id="99e8a-108">プロパティを <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 列挙体の適切な値に設定し <xref:System.Windows.Forms.RichTextBoxScrollBars> ます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="99e8a-109">値</span><span class="sxs-lookup"><span data-stu-id="99e8a-109">Value</span></span>|<span data-ttu-id="99e8a-110">説明</span><span class="sxs-lookup"><span data-stu-id="99e8a-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="99e8a-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (既定値)</span><span class="sxs-lookup"><span data-stu-id="99e8a-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="99e8a-112">テキストがコントロールの幅または長さを超えた場合にのみ、水平または垂直のスクロールバー、またはその両方を表示します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="99e8a-113">どの種類のスクロールバーも表示されません。</span><span class="sxs-lookup"><span data-stu-id="99e8a-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="99e8a-114">テキストがコントロールの幅を超えた場合にのみ、水平スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="99e8a-115">(これを行うには、 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティをに設定する必要があり `false` ます)。</span><span class="sxs-lookup"><span data-stu-id="99e8a-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="99e8a-116">テキストがコントロールの高さを超えた場合にのみ、垂直スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="99e8a-117">プロパティがに設定されている場合、水平スクロールバーを表示 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `false` します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="99e8a-118">テキストがコントロールの幅を超えていない場合、スクロールバーは淡色表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="99e8a-119">常に垂直スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="99e8a-120">テキストがコントロールの長さを超えていない場合、スクロールバーは淡色表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="99e8a-121">常に垂直スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="99e8a-122">プロパティがに設定されている場合、水平スクロールバーを表示 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `false` します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="99e8a-123">テキストがコントロールの幅または長さを超えていない場合、スクロールバーはグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3. <span data-ttu-id="99e8a-124"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="99e8a-125">値</span><span class="sxs-lookup"><span data-stu-id="99e8a-125">Value</span></span>|<span data-ttu-id="99e8a-126">説明</span><span class="sxs-lookup"><span data-stu-id="99e8a-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="99e8a-127">コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されないので、改行に達するまで右にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="99e8a-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="99e8a-128">上にある水平スクロールバーまたは両方を選択した場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="99e8a-129">`true` (既定)</span><span class="sxs-lookup"><span data-stu-id="99e8a-129">`true` (default)</span></span>|<span data-ttu-id="99e8a-130">コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="99e8a-131">水平スクロールバーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="99e8a-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="99e8a-132">1つ以上の段落を表示する場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="99e8a-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99e8a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="99e8a-133">See also</span></span>

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="99e8a-134">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="99e8a-134">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="99e8a-135">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="99e8a-135">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
