---
title: 内在コントロール
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 2865a3d85bd56151038ee90c18d199d3a584b5d4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974284"
---
# <a name="constituent-controls"></a>内在コントロール
ユーザー コントロールを構成するコントロール ("*内在コントロール*" と呼ばれます) は、カスタム グラフィックスのレンダリングに関してはそれほど柔軟ではありません。 すべての Windows フォームコントロールは、独自のメソッドを使用して独自のレンダリング <xref:System.Windows.Forms.Control.OnPaint%2A> を処理します。 このメソッドは保護されているため、開発者はアクセスできず、したがってコントロールが描画されるときに実行を防ぐことはできません。 ただし、これは、内在コントロールの外観に影響を与えるコードを追加できないという意味ではありません。 イベント ハンドラーを追加することで、追加のレンダリングを実現できます。 たとえば、という名前のボタンを使用してを作成したとし <xref:System.Windows.Forms.UserControl> `MyButton` ます。 によって提供された内容を超えて追加のレンダリングを使用する場合は、 <xref:System.Web.UI.WebControls.Button> 次のようなコードをユーザーコントロールに追加します。  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> などの一部の Windows フォームコントロール <xref:System.Windows.Forms.TextBox> は、Windows によって直接描画されます。 これらのインスタンスで <xref:System.Windows.Forms.Control.OnPaint%2A> は、メソッドは呼び出されません。したがって、上記の例は呼び出されません。  
  
 この例は、`MyButton.Paint` イベントが実行されるたびに実行するメソッドを作成し、それによって追加のグラフィカル表示をコントロールに追加します。 これにより `MyButton.OnPaint` の実行は妨げられないので、カスタム描画に加えて、ボタンによって通常実行されるすべての描画が実行されることに注意してください。 GDI+ テクノロジとカスタム レンダリングについて詳しくは、「[Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md)」 (GDI+ でのグラフィカル イメージの作成) をご覧ください。 コントロールの表示を独自のものにしたい場合の最善の方法は、継承コントロールを作成し、カスタム レンダリング コードをそこに記述するというものです。 詳しくは、「[ユーザー描画コントロール](user-drawn-controls.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [ユーザー描画コントロール](user-drawn-controls.md)
- [方法: 描画する Graphics オブジェクトを作成する](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [さまざまなカスタム コントロール](varieties-of-custom-controls.md)
