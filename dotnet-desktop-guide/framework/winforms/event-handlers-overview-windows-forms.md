---
title: イベント ハンドラーの概要
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ec8bc23ce8aba36ad456114ec645d4f0799f107f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981903"
---
# <a name="event-handlers-overview-windows-forms"></a>イベント ハンドラーの概要 (Windows フォーム)
イベントハンドラーは、イベントにバインドされているメソッドです。 イベントが発生すると、イベントハンドラー内のコードが実行されます。 各イベントハンドラーには、イベントを適切に処理できる2つのパラメーターが用意されています。 次の例は、コントロールのイベントのイベントハンドラーを示して <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> います。  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 最初のパラメーターであるは、 `sender` イベントを発生させたオブジェクトへの参照を提供します。 上の例の2番目のパラメーターは、 `e` 処理されるイベントに固有のオブジェクトを渡します。 オブジェクトのプロパティ (および場合によってはメソッド) を参照することにより、ドラッグアンドドロップイベントでマウスイベントや転送されるデータの場所などの情報を取得できます。  
  
 通常、各イベントは、2番目のパラメーターに対して異なるイベントオブジェクトの種類を持つイベントハンドラーを生成します。 イベントおよびイベントのイベントハンドラーの中には、 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> 2 番目のパラメーターと同じオブジェクト型を持つものもあります。 これらの種類のイベントでは、同じイベントハンドラーを使用して両方のイベントを処理できます。  
  
 また、同じイベントハンドラーを使用して、さまざまなコントロールに対して同じイベントを処理することもできます。 たとえば、フォームにコントロールのグループがある場合は、 <xref:System.Windows.Forms.RadioButton> イベントの1つのイベントハンドラーを作成し、 <xref:System.Windows.Forms.Control.Click> 各コントロールの <xref:System.Windows.Forms.Control.Click> イベントを1つのイベントハンドラーにバインドすることができます。 詳細については、「 [方法: Windows フォームの1つのイベントハンドラーに複数のイベントを接続](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)する」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [Windows フォーム内でのイベント ハンドラーの作成](creating-event-handlers-in-windows-forms.md)
- [イベントの概要](events-overview-windows-forms.md)
