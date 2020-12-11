---
title: コントロールでのイベントの定義
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: fabffc02ecf921eed428ec1ec452aa60c77b5987
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974192"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="8e691-102">Windows フォーム コントロールのイベントの定義</span><span class="sxs-lookup"><span data-stu-id="8e691-102">Defining an Event in Windows Forms Controls</span></span>

<span data-ttu-id="8e691-103">カスタムイベントの定義の詳細については、「 [イベント](/dotnet/standard/events/index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e691-103">For details about defining custom events, see [Events](/dotnet/standard/events/index).</span></span> <span data-ttu-id="8e691-104">関連データがないイベントを定義する場合、イベント データの基本型である <xref:System.EventArgs> を使用し、イベント デリゲートとして <xref:System.EventHandler> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e691-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="8e691-105">残りの作業は、イベントメンバーと、イベントを発生させる、保護された EventName メソッドを定義することです `On`  。</span><span class="sxs-lookup"><span data-stu-id="8e691-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="8e691-106">`FlashTrackBar` カスタム コントロールによる `ValueChanged` カスタム イベントの定義方法を示すコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e691-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="8e691-107">サンプルの完全なコードについては、 `FlashTrackBar` 「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e691-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate
   ' as the event delegate.
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged
   ' event when the value has actually
   ' changed. Derived controls can override this method.
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually
   // changed. Derived controls can override this method.
   protected virtual void OnValueChanged(EventArgs e)
   {  
       onValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e691-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e691-108">See also</span></span>

- [<span data-ttu-id="8e691-109">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="8e691-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="8e691-110">イベント</span><span class="sxs-lookup"><span data-stu-id="8e691-110">Events</span></span>](/dotnet/standard/events/index)
