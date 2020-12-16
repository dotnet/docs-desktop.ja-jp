---
title: どの修飾キーが押されたかを確認する
description: .NET 用 Windows フォームで、SHIFT、ALT、CTRL の各キーが押されたことを検出する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.openlocfilehash: 7feda0f604e1cb40b34f7bf42aa122d817a5a95e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942262"
---
# <a name="how-to-check-for-modifier-key-presses-windows-forms-net"></a><span data-ttu-id="2d02e-103">修飾キーの押下を確認する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="2d02e-103">How to check for modifier key presses (Windows Forms .NET)</span></span>

<span data-ttu-id="2d02e-104">ユーザーがアプリケーションにキーを入力すると、<kbd>SHIFT</kbd>、<kbd>ALT</kbd>、<kbd>CTRL</kbd> などの修飾キーが押されたかどうかを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="2d02e-104">As the user types keys into your application, you can monitor for pressed modifier keys such as the <kbd>SHIFT</kbd>, <kbd>ALT</kbd>, and <kbd>CTRL</kbd>.</span></span> <span data-ttu-id="2d02e-105">修飾キーが他のキーと組み合わせて押されても、マウス クリックによっても、アプリケーションが適切に応答できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2d02e-105">When a modifier key is pressed in combination with other keys or even a mouse click, your application can respond appropriately.</span></span> <span data-ttu-id="2d02e-106">たとえば、<kbd>S</kbd> キーを押すと、画面に "s" が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2d02e-106">For example, pressing the <kbd>S</kbd> key may cause an "s" to appear on the screen.</span></span> <span data-ttu-id="2d02e-107">そうではなく、<kbd>CTRL + S</kbd> キーが押される場合には、現在のドキュメントが保存されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2d02e-107">If the keys <kbd>CTRL+S</kbd> are pressed, instead, the current document may be saved.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="2d02e-108"><xref:System.Windows.Forms.Control.KeyDown> イベントを処理する場合、イベント ハンドラーが受信する <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> プロパティによって、どの修飾キーが押されているかが特定されます。</span><span class="sxs-lookup"><span data-stu-id="2d02e-108">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> property received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="2d02e-109">また、ビットごとの OR と組み合わせた修飾キーと共に押された文字が、<xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> プロパティによって特定されます。</span><span class="sxs-lookup"><span data-stu-id="2d02e-109">Also, the <xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> property specifies the character that was pressed along with any modifier keys combined with a bitwise OR.</span></span>

<span data-ttu-id="2d02e-110"><xref:System.Windows.Forms.Control.KeyPress> イベントまたはマウス イベントを処理している場合、イベント ハンドラーがこの情報を受信することはありません。</span><span class="sxs-lookup"><span data-stu-id="2d02e-110">If you're handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler doesn't receive this information.</span></span> <span data-ttu-id="2d02e-111"><xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.ModifierKeys%2A> プロパティを使用して、キー修飾子を検出します。</span><span class="sxs-lookup"><span data-stu-id="2d02e-111">Use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class to detect a key modifier.</span></span> <span data-ttu-id="2d02e-112">どちらの場合も、適切な <xref:System.Windows.Forms.Keys> 値とテスト対象の値のビットごとの AND を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d02e-112">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you're testing.</span></span> <span data-ttu-id="2d02e-113"><xref:System.Windows.Forms.Keys> 列挙型を使用すると、各修飾キーのバリエーションが増えるため、ビットごとの AND の確認には、正しい値を使用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2d02e-113">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it's important that you do the bitwise AND check with the correct value.</span></span>

<span data-ttu-id="2d02e-114">たとえば、次のキー値は <kbd>SHIFT</kbd> キーを表します。</span><span class="sxs-lookup"><span data-stu-id="2d02e-114">For example, the <kbd>SHIFT</kbd> key is represented by the following key values:</span></span>

- <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.ShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.RShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.LShiftKey?displayProperty=nameWithType>

<span data-ttu-id="2d02e-115">修飾キーとして <kbd>SHIFT</kbd> をテストする場合の正しい値は、<xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="2d02e-115">The correct value to test <kbd>SHIFT</kbd> as a modifier key is <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2d02e-116">同様に、修飾子として <kbd>CTRL</kbd> と <kbd>ALT</kbd> をテストする場合は、<xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> 値と <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> 値をそれぞれ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d02e-116">Similarly, to test for <kbd>CTRL</kbd> and <kbd>ALT</kbd> as modifiers you should use the <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> and <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> values, respectively.</span></span>

## <a name="detect-modifier-key"></a><span data-ttu-id="2d02e-117">修飾キーを検出する</span><span class="sxs-lookup"><span data-stu-id="2d02e-117">Detect modifier key</span></span>

<span data-ttu-id="2d02e-118"><xref:System.Windows.Forms.Control.ModifierKeys%2A> プロパティと <xref:System.Windows.Forms.Keys> 列挙値をビットごとの AND 演算子と比較して、修飾キーが押されているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d02e-118">Detect if a modifier key is pressed by comparing the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and the <xref:System.Windows.Forms.Keys> enumeration value with a bitwise AND operator.</span></span>

<span data-ttu-id="2d02e-119">次のコード例では、<xref:System.Windows.Forms.Control.KeyPress> イベント ハンドラーと <xref:System.Windows.Forms.Control.KeyDown> のイベント ハンドラー内で、<kbd>SHIFT</kbd> キーが押されているかどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2d02e-119">The following code example shows how to determine whether the <kbd>SHIFT</kbd> key is pressed within the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyDown> event handlers.</span></span>

:::code language="csharp" source="snippets/how-to-check-modifier-key/csharp/Form1.cs" id="DetectModifier":::
:::code language="vb" source="snippets/how-to-check-modifier-key/vb/Form1.vb" id="DetectModifier":::

## <a name="see-also"></a><span data-ttu-id="2d02e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d02e-120">See also</span></span>

- [<span data-ttu-id="2d02e-121">キーボードの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="2d02e-121">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="2d02e-122">キーボード イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="2d02e-122">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
