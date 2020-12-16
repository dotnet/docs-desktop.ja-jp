---
title: マウス ポインターを管理する方法
description: .NET 用の Windows フォームで、マウス ポインターにアクセス、制御、および変更する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.openlocfilehash: b4439c34bf7a7f41a94ce5ec5971520d9c82e469
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942298"
---
# <a name="manage-mouse-pointers-windows-forms-net"></a><span data-ttu-id="4a49c-103">マウス ポインターを管理する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="4a49c-103">Manage mouse pointers (Windows Forms .NET)</span></span>

<span data-ttu-id="4a49c-104">マウス *ポインター* (カーソルと呼ばれることもあります) は、マウスで行われたユーザー入力に対し、画面上のフォーカス ポイントを指定するビットマップです。</span><span class="sxs-lookup"><span data-stu-id="4a49c-104">The mouse *pointer*, which is sometimes referred to as the cursor, is a bitmap that specifies a focus point on the screen for user input with the mouse.</span></span> <span data-ttu-id="4a49c-105">このトピックでは、Windows フォームにおけるマウス ポインターの概要および、マウス ポインターを変更および制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a49c-105">This topic provides an overview of the mouse pointer in Windows Forms and describes some of the ways to modify and control the mouse pointer.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessing-the-mouse-pointer"></a><span data-ttu-id="4a49c-106">マウス ポインターにアクセスする</span><span class="sxs-lookup"><span data-stu-id="4a49c-106">Accessing the mouse pointer</span></span>

<span data-ttu-id="4a49c-107">マウス ポインターは <xref:System.Windows.Forms.Cursor> クラスによって表され、各 <xref:System.Windows.Forms.Control> には、そのコントロールのポインターを指定する <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="4a49c-107">The mouse pointer is represented by the <xref:System.Windows.Forms.Cursor> class, and each <xref:System.Windows.Forms.Control> has a <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> property that specifies the pointer for that control.</span></span> <span data-ttu-id="4a49c-108"><xref:System.Windows.Forms.Cursor> クラスには、<xref:System.Windows.Forms.Cursor.Position%2A> や <xref:System.Windows.Forms.Cursor.HotSpot%2A> プロパティなどのポインターを表すプロパティや、<xref:System.Windows.Forms.Cursor.Show%2A>、<xref:System.Windows.Forms.Cursor.Hide%2A>、<xref:System.Windows.Forms.Cursor.DrawStretched%2A> メソッドなどのポインターの外観を変更するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="4a49c-108">The <xref:System.Windows.Forms.Cursor> class contains properties that describe the pointer, such as the <xref:System.Windows.Forms.Cursor.Position%2A> and <xref:System.Windows.Forms.Cursor.HotSpot%2A> properties, and methods that can modify the appearance of the pointer, such as the <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, and <xref:System.Windows.Forms.Cursor.DrawStretched%2A> methods.</span></span>

<span data-ttu-id="4a49c-109">次の例では、カーソルがボタン上にあると、カーソルが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="4a49c-109">The following example hides the cursor when the cursor is over a button:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="ShowHideCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="ShowHideCursor":::

## <a name="controlling-the-mouse-pointer"></a><span data-ttu-id="4a49c-110">マウス ポインターを制御する</span><span class="sxs-lookup"><span data-stu-id="4a49c-110">Controlling the mouse pointer</span></span>

<span data-ttu-id="4a49c-111">マウス ポインターを使用できる領域を制限したり、マウスの位置を変更したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a49c-111">Sometimes you may want to limit the area in which the mouse pointer can be used or change the position the mouse.</span></span> <span data-ttu-id="4a49c-112"><xref:System.Windows.Forms.Cursor> の <xref:System.Windows.Forms.Cursor.Position%2A> プロパティを使用すると、マウスの現在の位置を取得または設定できます。</span><span class="sxs-lookup"><span data-stu-id="4a49c-112">You can get or set the current location of the mouse using the <xref:System.Windows.Forms.Cursor.Position%2A> property of the <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="4a49c-113">また、<xref:System.Windows.Forms.Cursor.Clip%2A> プロパティを設定して、マウス ポインターを使用できる領域を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="4a49c-113">In addition, you can limit the area the mouse pointer can be used be setting the <xref:System.Windows.Forms.Cursor.Clip%2A> property.</span></span> <span data-ttu-id="4a49c-114">クリップ領域は、既定で画面全体です。</span><span class="sxs-lookup"><span data-stu-id="4a49c-114">The clip area, by default, is the entire screen.</span></span>

<span data-ttu-id="4a49c-115">次の例では、クリック時にマウス ポインターが 2 つのボタン間に配置されます。</span><span class="sxs-lookup"><span data-stu-id="4a49c-115">The following example positions the mouse pointer between two buttons when they are clicked:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="MoveCursor":::

## <a name="changing-the-mouse-pointer"></a><span data-ttu-id="4a49c-116">マウス ポインターを変更する</span><span class="sxs-lookup"><span data-stu-id="4a49c-116">Changing the mouse pointer</span></span>

<span data-ttu-id="4a49c-117">ユーザーにフィードバックを提供する重要な方法として、マウス ポインターを変更する方法があります。</span><span class="sxs-lookup"><span data-stu-id="4a49c-117">Changing the mouse pointer is an important way of providing feedback to the user.</span></span> <span data-ttu-id="4a49c-118">たとえば、<xref:System.Windows.Forms.Control.MouseEnter> および <xref:System.Windows.Forms.Control.MouseLeave> イベントのハンドラーでマウス ポインターを変更し、計算が行われていることをユーザーに通知して、コントロールでのユーザー操作を制限できます。</span><span class="sxs-lookup"><span data-stu-id="4a49c-118">For example, the mouse pointer can be modified in the handlers of the <xref:System.Windows.Forms.Control.MouseEnter> and <xref:System.Windows.Forms.Control.MouseLeave> events to tell the user that computations are occurring and to limit user interaction in the control.</span></span> <span data-ttu-id="4a49c-119">アプリケーションでドラッグアンドドロップ操作が行われている場合などのシステム イベントのために、マウス ポインターが変わることもあります。</span><span class="sxs-lookup"><span data-stu-id="4a49c-119">Sometimes, the mouse pointer will change because of system events, such as when your application is involved in a drag-and-drop operation.</span></span>

<span data-ttu-id="4a49c-120">マウス ポインターを変更する第一の方法は、コントロールの <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> または <xref:System.Windows.Forms.Control.DefaultCursor%2A> プロパティを新しい <xref:System.Windows.Forms.Cursor> に設定することです。</span><span class="sxs-lookup"><span data-stu-id="4a49c-120">The primary way to change the mouse pointer is by setting the <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.Control.DefaultCursor%2A> property of a control to a new <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="4a49c-121">マウス ポインターの変更例については、<xref:System.Windows.Forms.Cursor> クラスのコード例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a49c-121">For examples of changing the mouse pointer, see the code example in the <xref:System.Windows.Forms.Cursor> class.</span></span> <span data-ttu-id="4a49c-122"><xref:System.Windows.Forms.Cursors> クラスでは、これ以外に手のようなポインターなど、さまざまな種類のポインターに対する <xref:System.Windows.Forms.Cursor> オブジェクトのセットを公開しています。</span><span class="sxs-lookup"><span data-stu-id="4a49c-122">In addition, the <xref:System.Windows.Forms.Cursors> class exposes a set of <xref:System.Windows.Forms.Cursor> objects for many different types of pointers, such as a pointer that resembles a hand.</span></span>

<span data-ttu-id="4a49c-123">次の例では、ボタンのマウス ポインターのカーソルが手の形に変更されます。</span><span class="sxs-lookup"><span data-stu-id="4a49c-123">The following example changes the cursor of the mouse pointer for a button to a hand:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="SetControlCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="SetControlCursor":::

<span data-ttu-id="4a49c-124">マウス ポインターがコントロール上にあるときに常に砂時計のような待機ポインターを表示するには、<xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.UseWaitCursor%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a49c-124">To display the wait pointer, which resembles an hourglass, whenever the mouse pointer is on the control, use the <xref:System.Windows.Forms.Control.UseWaitCursor%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a49c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a49c-125">See also</span></span>

- [<span data-ttu-id="4a49c-126">マウスの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="4a49c-126">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="4a49c-127">マウス イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="4a49c-127">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="4a49c-128">クリックとダブルクリックを区別する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="4a49c-128">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>](how-to-distinguish-between-clicks-and-double-clicks.md)
- [<span data-ttu-id="4a49c-129">マウス イベントをシミュレートする方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="4a49c-129">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>
