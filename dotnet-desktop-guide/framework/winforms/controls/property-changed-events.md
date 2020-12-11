---
title: プロパティ変更イベント
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 939972713ad95e9302c436268f4a6288a659ca6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983423"
---
# <a name="property-changed-events"></a><span data-ttu-id="37789-102">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="37789-102">Property-Changed Events</span></span>

<span data-ttu-id="37789-103">*Propertyname* という名前のプロパティが変更されたときに、コントロールが通知を送信するようにするには、 *propertyname* という名前のイベントと `Changed` `On` 、イベントを発生させる *propertyname* という名前のメソッドを定義し `Changed` ます。</span><span class="sxs-lookup"><span data-stu-id="37789-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="37789-104">Windows フォームの名前付け規則は、 *変更さ* れた単語をプロパティの名前に追加することです。</span><span class="sxs-lookup"><span data-stu-id="37789-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="37789-105">プロパティ変更イベントに関連付けられたイベントデリゲート型は <xref:System.EventHandler> で、イベントデータ型は <xref:System.EventArgs> です。</span><span class="sxs-lookup"><span data-stu-id="37789-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="37789-106">基底クラスは、、、、などの <xref:System.Windows.Forms.Control> 多くのプロパティ変更イベントを定義し <xref:System.Windows.Forms.Control.BackColorChanged> <xref:System.Windows.Forms.Control.BackgroundImageChanged> <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.LocationChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="37789-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="37789-107">イベントの背景情報については、「 [Windows フォームコントロールの](events-in-windows-forms-controls.md)[イベント](/dotnet/standard/events/index)とイベント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37789-107">For background information about events, see [Events](/dotnet/standard/events/index) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="37789-108">プロパティ変更イベントは、コントロールのコンシューマーが変更に応答するイベントハンドラーをアタッチできるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="37789-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="37789-109">コントロールが、発生したプロパティ変更イベントに応答する必要がある場合は、 `On`  `Changed` デリゲートをイベントにアタッチする代わりに、対応する PropertyName メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="37789-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="37789-110">通常、コントロールは、他のプロパティを更新するか、その描画サーフェイスの一部またはすべてを再描画することによって、プロパティ変更イベントに応答します。</span><span class="sxs-lookup"><span data-stu-id="37789-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="37789-111">次の例は、 `FlashTrackBar` カスタムコントロールが、継承元のプロパティ変更イベントの一部に対してどのように応答するかを示して <xref:System.Windows.Forms.Control> います。</span><span class="sxs-lookup"><span data-stu-id="37789-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="37789-112">完全なサンプルについては、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37789-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="37789-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="37789-113">See also</span></span>

- [<span data-ttu-id="37789-114">イベント</span><span class="sxs-lookup"><span data-stu-id="37789-114">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="37789-115">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="37789-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="37789-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="37789-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
