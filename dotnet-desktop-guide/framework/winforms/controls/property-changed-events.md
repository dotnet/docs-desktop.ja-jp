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
# <a name="property-changed-events"></a>プロパティ変更イベント

*Propertyname* という名前のプロパティが変更されたときに、コントロールが通知を送信するようにするには、 *propertyname* という名前のイベントと `Changed` `On` 、イベントを発生させる *propertyname* という名前のメソッドを定義し `Changed` ます。 Windows フォームの名前付け規則は、 *変更さ* れた単語をプロパティの名前に追加することです。 プロパティ変更イベントに関連付けられたイベントデリゲート型は <xref:System.EventHandler> で、イベントデータ型は <xref:System.EventArgs> です。 基底クラスは、、、、などの <xref:System.Windows.Forms.Control> 多くのプロパティ変更イベントを定義し <xref:System.Windows.Forms.Control.BackColorChanged> <xref:System.Windows.Forms.Control.BackgroundImageChanged> <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.LocationChanged> ます。 イベントの背景情報については、「 [Windows フォームコントロールの](events-in-windows-forms-controls.md)[イベント](/dotnet/standard/events/index)とイベント」を参照してください。  
  
 プロパティ変更イベントは、コントロールのコンシューマーが変更に応答するイベントハンドラーをアタッチできるようにするために役立ちます。 コントロールが、発生したプロパティ変更イベントに応答する必要がある場合は、 `On`  `Changed` デリゲートをイベントにアタッチする代わりに、対応する PropertyName メソッドをオーバーライドします。 通常、コントロールは、他のプロパティを更新するか、その描画サーフェイスの一部またはすべてを再描画することによって、プロパティ変更イベントに応答します。  
  
 次の例は、 `FlashTrackBar` カスタムコントロールが、継承元のプロパティ変更イベントの一部に対してどのように応答するかを示して <xref:System.Windows.Forms.Control> います。 完全なサンプルについては、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>関連項目

- [イベント](/dotnet/standard/events/index)
- [Windows フォーム コントロールのイベント](events-in-windows-forms-controls.md)
- [Windows フォーム コントロールのプロパティ](properties-in-windows-forms-controls.md)
