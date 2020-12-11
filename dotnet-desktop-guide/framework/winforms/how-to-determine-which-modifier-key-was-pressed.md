---
title: '方法: どの修飾子キーが押されたかを判断する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
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
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 9140834b4849ecb143ac57a6f6ae20e2d870859b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974347"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="e3366-102">方法: どの修飾子キーが押されたかを判断する</span><span class="sxs-lookup"><span data-stu-id="e3366-102">How to: Determine Which Modifier Key Was Pressed</span></span>

<span data-ttu-id="e3366-103">ユーザーのキーストロークを受け入れるアプリケーションを作成する場合、SHIFT キー、ALT キー、CTRL キーなどの修飾子キーを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3366-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="e3366-104">修飾子キーを他のキーと組み合わせて押すか、マウスをクリックすると、アプリケーションが適切に応答できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e3366-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="e3366-105">たとえば、文字 S が押されている場合、画面に "s" が表示されることがありますが、CTRL + S キーを押すと、現在のドキュメントが保存されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3366-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="e3366-106">イベントを処理する場合は、 <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> <xref:System.Windows.Forms.KeyEventArgs> イベントハンドラーによって受信されるのプロパティによって、どの修飾子キーが押されたかが指定されます。</span><span class="sxs-lookup"><span data-stu-id="e3366-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="e3366-107">または、 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> のプロパティは、 <xref:System.Windows.Forms.KeyEventArgs> 押された文字と、ビットごとの or を組み合わせた修飾子キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3366-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="e3366-108">ただし、イベントまたはマウスイベントを処理している場合、 <xref:System.Windows.Forms.Control.KeyPress> イベントハンドラーはこの情報を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="e3366-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="e3366-109">この場合は、クラスのプロパティを使用する必要があり <xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Control> ます。</span><span class="sxs-lookup"><span data-stu-id="e3366-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="e3366-110">どちらの場合も、適切な <xref:System.Windows.Forms.Keys> 値とテストする値のビットごとの and を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3366-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="e3366-111"><xref:System.Windows.Forms.Keys>列挙体は各修飾子キーのバリエーションを提供するので、ビットごとの and を正しい値で実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e3366-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="e3366-112">たとえば、shift キーは、、およびによって表され <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.ShiftKey> <xref:System.Windows.Forms.Keys.RShiftKey> <xref:System.Windows.Forms.Keys.LShiftKey> ます。また、シフトを修飾子キーとしてテストするための正しい値は <xref:System.Windows.Forms.Keys.Shift> です。</span><span class="sxs-lookup"><span data-stu-id="e3366-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="e3366-113">同様に、CTRL と ALT を修飾子としてテストするには、 <xref:System.Windows.Forms.Keys.Control> それぞれとの値をそれぞれ使用する必要があり <xref:System.Windows.Forms.Keys.Alt> ます。</span><span class="sxs-lookup"><span data-stu-id="e3366-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3366-114">Visual Basic プログラマは、プロパティを使用してキー情報にアクセスすることもできます。 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A></span><span class="sxs-lookup"><span data-stu-id="e3366-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="e3366-115">どの修飾子キーが押されたかを調べるには</span><span class="sxs-lookup"><span data-stu-id="e3366-115">To determine which modifier key was pressed</span></span>  
  
- <span data-ttu-id="e3366-116">ビットごとの `AND` 演算子とプロパティを使用し、列挙体の値を使用して、 <xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Keys> 特定の修飾子キーが押されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e3366-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="e3366-117">次のコード例は、イベントハンドラー内で SHIFT キーが押されているかどうかを確認する方法を示して <xref:System.Windows.Forms.Control.KeyPress> います。</span><span class="sxs-lookup"><span data-stu-id="e3366-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e3366-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3366-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="e3366-119">Windows フォーム アプリケーションにおけるキーボード入力</span><span class="sxs-lookup"><span data-stu-id="e3366-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- <span data-ttu-id="e3366-120">[方法: Visual Basic で CapsLock が On であるかどうかを確認する](/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e3366-120">[How to: Determine If CapsLock is On in Visual Basic](/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span></span>
