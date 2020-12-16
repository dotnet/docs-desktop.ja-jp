---
title: マウス イベントをシミュレートする方法
description: .NET の Windows フォームでマウス イベントをシミュレートする方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 443611163d33a266b3c49d03df13131c994b0bd3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942295"
---
# <a name="how-to-simulate-mouse-events-windows-forms-net"></a><span data-ttu-id="853e6-103">マウス イベントをシミュレートする方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="853e6-103">How to simulate mouse events (Windows Forms .NET)</span></span>

<span data-ttu-id="853e6-104">Windows フォームでのマウス イベントのシミュレートは、キーボード イベントをシミュレートするほど簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="853e6-104">Simulating mouse events in Windows Forms isn't as straight forward as simulating keyboard events.</span></span> <span data-ttu-id="853e6-105">Windows フォームには、マウスを移動してマウスクリックのアクションを呼び出すヘルパー クラスがありません。</span><span class="sxs-lookup"><span data-stu-id="853e6-105">Windows Forms doesn't provide a helper class to move the mouse and invoke mouse-click actions.</span></span> <span data-ttu-id="853e6-106">マウスは、Windows のネイティブ メソッドを使用してのみ制御することができます。</span><span class="sxs-lookup"><span data-stu-id="853e6-106">The only option for controlling the mouse is to use native Windows methods.</span></span> <span data-ttu-id="853e6-107">カスタム コントロールまたはフォームを使用している場合は、マウス イベントをシミュレートできますが、マウスを直接制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="853e6-107">If you're working with a custom control or a form, you can simulate a mouse event, but you can't directly control the mouse.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="events"></a><span data-ttu-id="853e6-108">イベント</span><span class="sxs-lookup"><span data-stu-id="853e6-108">Events</span></span>

<span data-ttu-id="853e6-109">ほとんどのイベントには、それらを呼び出す対応するメソッドがあり、`OnMouseMove` のように `On` の後に `EventName` が続く名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="853e6-109">Most events have a corresponding method that invokes them, named in the pattern of `On` followed by `EventName`, such as `OnMouseMove`.</span></span> <span data-ttu-id="853e6-110">これらのメソッドは保護されており、コントロールまたはフォームのコンテキストの外部からアクセスすることはできないため、このオプションは、カスタム コントロールまたはフォーム内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="853e6-110">This option is only possible within custom controls or forms, because these methods are protected and can't be accessed from outside the context of the control or form.</span></span> <span data-ttu-id="853e6-111">`OnMouseMove` などのメソッドを使用する場合には、実際にマウスを制御したり、コントロールとやり取りしたりできず、関連するイベントが発生するだけという欠点があります。</span><span class="sxs-lookup"><span data-stu-id="853e6-111">The disadvantage to using a method such as `OnMouseMove` is that it doesn't actually control the mouse or interact with the control, it simply raises the associated event.</span></span> <span data-ttu-id="853e6-112">たとえば、<xref:System.Windows.Forms.ListBox> 内の項目にマウス ポインターを重ねた状態をシミュレートしたい場合、`OnMouseMove` と `ListBox` は、カーソルの下で強調表示されている項目に視覚的に反応しません。</span><span class="sxs-lookup"><span data-stu-id="853e6-112">For example, if you wanted to simulate hovering over an item in a <xref:System.Windows.Forms.ListBox>, `OnMouseMove` and the `ListBox` doesn't visually react with a highlighted item under the cursor.</span></span>

<span data-ttu-id="853e6-113">これらの保護されたメソッドは、マウス イベントをシミュレートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="853e6-113">These protected methods are available to simulate mouse events.</span></span>

- `OnMouseDown`
- `OnMouseEnter`
- `OnMouseHover`
- `OnMouseLeave`
- `OnMouseMove`
- `OnMouseUp`
- `OnMouseWheel`
- `OnMouseClick`
- `OnMouseDoubleClick`

<span data-ttu-id="853e6-114">これらのイベントの詳細については、「[マウス イベントの使用 (Windows フォーム .NET)](events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="853e6-114">For more information about these events, see [Using mouse events (Windows Forms .NET)](events.md)</span></span>

## <a name="invoke-a-click"></a><span data-ttu-id="853e6-115">クリックを呼び出す</span><span class="sxs-lookup"><span data-stu-id="853e6-115">Invoke a click</span></span>

<span data-ttu-id="853e6-116">ユーザー コードを呼び出すボタンやチェック状態を変更するチェックボックスなどのように、ほとんどのコントロールはクリックされると何らかの動作を実行するので、Windows フォームにはクリックを簡単にトリガーする方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="853e6-116">Considering most controls do something when clicked, like a button calling user code, or checkbox change its checked state, Windows Forms provides an easy way to trigger the click.</span></span> <span data-ttu-id="853e6-117">コンボボックスなどの一部のコントロールでは、クリックしても特別な処理は行われず、このコントロールにクリックをシミュレートしても何も作用はありません。</span><span class="sxs-lookup"><span data-stu-id="853e6-117">Some controls, such as a combobox, don't do anything special when clicked and simulating a click has no effect on the control.</span></span>

### <a name="performclick"></a><span data-ttu-id="853e6-118">PerformClick</span><span class="sxs-lookup"><span data-stu-id="853e6-118">PerformClick</span></span>

<span data-ttu-id="853e6-119"><xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> インターフェイスには、コントロールのクリックをシミュレートする <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> メソッドが実装されています。</span><span class="sxs-lookup"><span data-stu-id="853e6-119">The <xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> interface provides the <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> method which simulates a click on the control.</span></span> <span data-ttu-id="853e6-120">このインターフェイスは、<xref:System.Windows.Forms.Button?displayProperty=nameWithType> と <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> の両コントロールに実装されています。</span><span class="sxs-lookup"><span data-stu-id="853e6-120">Both the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> and <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> controls implement this interface.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="PerformClick":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="PerformClick":::

### <a name="invokeclick"></a><span data-ttu-id="853e6-121">InvokeClick</span><span class="sxs-lookup"><span data-stu-id="853e6-121">InvokeClick</span></span>

<span data-ttu-id="853e6-122">フォームまたはカスタム コントロールでは、マウスのクリックのシミュレートに <xref:System.Windows.Forms.Control.InvokeOnClick%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="853e6-122">With a form a custom control, use the <xref:System.Windows.Forms.Control.InvokeOnClick%2A> method to simulate a mouse click.</span></span> <span data-ttu-id="853e6-123">これは、フォームまたは派生したカスタム コントロールからのみ呼び出すことができる保護されたメソッドです。</span><span class="sxs-lookup"><span data-stu-id="853e6-123">This is a protected method that can only be called from within the form or a derived custom control.</span></span>

<span data-ttu-id="853e6-124">たとえば、次のコードでは、`button1` からチェックボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="853e6-124">For example, the following code clicks a checkbox from `button1`.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ClickCheckbox":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ClickCheckbox":::

## <a name="use-native-windows-methods"></a><span data-ttu-id="853e6-125">Windows のネイティブ メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="853e6-125">Use native Windows methods</span></span>

<span data-ttu-id="853e6-126">Windows には、マウスの動きとクリックをシミュレートするために呼び出せる、[`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) や [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos) などのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="853e6-126">Windows provides methods you can call to simulate mouse movements and clicks such as [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) and [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos).</span></span> <span data-ttu-id="853e6-127">次の例は、マウス カーソルをコントロールの中央に移動します。</span><span class="sxs-lookup"><span data-stu-id="853e6-127">The following example moves the mouse cursor to the center of a control:</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="MoveCursor":::

## <a name="see-also"></a><span data-ttu-id="853e6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="853e6-128">See also</span></span>

- [<span data-ttu-id="853e6-129">マウスの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="853e6-129">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="853e6-130">マウス イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="853e6-130">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="853e6-131">クリックとダブルクリックを区別する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="853e6-131">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>](how-to-distinguish-between-clicks-and-double-clicks.md)
- [<span data-ttu-id="853e6-132">マウス ポインターを管理する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="853e6-132">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
