---
title: ユーザー描画コントロール
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984031"
---
# <a name="user-drawn-controls"></a>ユーザー描画コントロール
.NET Framework には、独自のコントロールを簡単に開発する機能が用意されています。 コードによって連結された一連の標準コントロールであるユーザーコントロールを作成することも、独自のコントロールを最初からデザインすることもできます。 継承を使用して、既存のコントロールから継承し、固有の機能に追加するコントロールを作成することもできます。 どのような方法を使用する場合でも、.NET Framework は、作成するコントロールのカスタムグラフィカルインターフェイスを描画する機能を提供します。  
  
 コントロールを描画するには、コントロールのメソッドでコードを実行し <xref:System.Windows.Forms.Control.OnPaint%2A> ます。 メソッドの1つの引数 <xref:System.Windows.Forms.Control.OnPaint%2A> は、 <xref:System.Windows.Forms.PaintEventArgs> コントロールを表示するために必要なすべての情報と機能を提供するオブジェクトです。 は、 <xref:System.Windows.Forms.PaintEventArgs> コントロールのレンダリングで使用される2つのプリンシパルオブジェクトをプロパティとして提供します。  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object-描画されるコントロールの部分を表す四角形。 コントロール全体、またはコントロールの描画方法に応じたコントロールの一部を指定できます。  
  
- <xref:System.Drawing.Graphics> object-コントロールを描画するために必要な機能を提供する複数のグラフィックス指向オブジェクトおよびメソッドをカプセル化します。  
  
 <xref:System.Drawing.Graphics>オブジェクトとその使用方法の詳細については、「[方法: 描画するためのグラフィックスオブジェクトを作成する](../advanced/how-to-create-graphics-objects-for-drawing.md)」を参照してください。  
  
 イベントは、 <xref:System.Windows.Forms.Control.OnPaint%2A> 画面上でコントロールが描画またはリフレッシュされるたびに発生し、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> オブジェクトは描画が行われる四角形を表します。 コントロール全体を更新する必要がある場合、は <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> コントロール全体のサイズを表します。 ただし、コントロールの一部だけを更新する必要がある場合、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> オブジェクトは再描画する必要がある領域のみを表します。 このような場合の例として、コントロールがユーザーインターフェイスの別のコントロールまたはフォームによって部分的に隠されている場合があります。  
  
 クラスから継承する場合は、 <xref:System.Windows.Forms.Control> メソッドをオーバーライド <xref:System.Windows.Forms.Control.OnPaint%2A> し、内にグラフィックスレンダリングコードを提供する必要があります。 ユーザーコントロールまたは継承されたコントロールにカスタムグラフィカルインターフェイスを提供する場合は、メソッドをオーバーライドすることによってもでき <xref:System.Windows.Forms.Control.OnPaint%2A> ます。 例を次に示します。  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,
         this.Size));  
   }
}  
```  
  
 前の例では、非常に単純なグラフィカル表示を使用してコントロールを表示する方法を示しています。 <xref:System.Windows.Forms.Control.OnPaint%2A>基底クラスのメソッドを呼び出し、 <xref:System.Drawing.Pen> 描画に使用するオブジェクトを作成します。最後に、コントロールのとによって決定される四角形に楕円を描画し <xref:System.Windows.Forms.Control.Location%2A> <xref:System.Windows.Forms.Control.Size%2A> ます。 ほとんどのレンダリングコードは、これよりもかなり複雑になりますが、この例では、オブジェクト内に含まれるオブジェクトの使用方法を示して <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> います。 またはのように、既にグラフィック表示を使用しているクラスから継承 <xref:System.Windows.Forms.UserControl> していて、 <xref:System.Windows.Forms.Button> その表現をレンダリングに組み込む必要がない場合は、基底クラスのメソッドを呼び出さないように注意してください <xref:System.Windows.Forms.Control.OnPaint%2A> 。  
  
 コントロールのメソッドのコードは、 <xref:System.Windows.Forms.Control.OnPaint%2A> コントロールが最初に描画されたときと、コントロールが更新されるたびに実行されます。 コントロールがサイズ変更されるたびに再描画されるようにするには、コントロールのコンストラクターに次の行を追加します。  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>四角形以外のコントロールを実装するには、プロパティを使用します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [方法: 描画する Graphics オブジェクトを作成する](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [内在コントロール](constituent-controls.md)
- [さまざまなカスタム コントロール](varieties-of-custom-controls.md)
