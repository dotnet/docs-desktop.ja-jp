---
title: コントロールをレンダリングする
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 86e219723dde8c10a8cc0d4ee7bdf149cde399bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982472"
---
# <a name="rendering-a-windows-forms-control"></a>Windows フォーム コントロールのレンダリング

レンダリングとは、ユーザーの画面で視覚的表現を作成するプロセスを指します。 Windows フォームは、GDI (新しい Windows グラフィックスライブラリ) を使用してレンダリングを行います。 GDI へのアクセスを提供するマネージクラスは、 <xref:System.Drawing?displayProperty=nameWithType> 名前空間とその副名前空間にあります。  
  
 コントロールのレンダリングには、次の要素が含まれます。  
  
- 基本クラスによって提供される描画機能 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。  
  
- GDI グラフィックスライブラリの重要な要素。  
  
- 描画領域のジオメトリ。  
  
- グラフィックスリソースを解放する手順。  
  
## <a name="drawing-functionality-provided-by-control"></a>コントロールによって提供される描画機能  

 基底クラスは、 <xref:System.Windows.Forms.Control> イベントを通じて描画機能を提供し <xref:System.Windows.Forms.Control.Paint> ます。 コントロールは、 <xref:System.Windows.Forms.Control.Paint> 表示を更新する必要があるときに常にイベントを発生させます。 .NET Framework のイベントの詳細については、「 [イベントの処理と発生](/dotnet/standard/events/index)」を参照してください。  
  
 イベントのイベントデータクラスは、 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> コントロールを描画するために必要なデータ (グラフィックスオブジェクトへのハンドル、および描画する領域を表す四角形オブジェクトを保持します) を保持します。 これらのオブジェクトは、次のコードフラグメントに太字で示されています。  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics> は、このトピックの後半の「GDI の説明」で説明されているように、描画機能をカプセル化するマネージクラスです。 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>は構造体のインスタンスであり、 <xref:System.Drawing.Rectangle> コントロールが描画できる領域を定義します。 コントロール開発者は、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> このトピックで後述する「ジオメトリの説明」で説明されているように、コントロールのプロパティを使用してを計算できます。  
  
 コントロールは、継承元のメソッドをオーバーライドすることにより、レンダリングロジックを提供する必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> ます。 <xref:System.Windows.Forms.Control.OnPaint%2A> グラフィックスオブジェクトと、に <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 渡されるインスタンスのプロパティを通じて描画する四角形へのアクセスを取得し <xref:System.Windows.Forms.PaintEventArgs> ます。  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>基底クラスのメソッドは <xref:System.Windows.Forms.Control> 描画機能を実装しませんが、イベントに登録されているイベントデリゲートを呼び出すだけです <xref:System.Windows.Forms.Control.Paint> 。 をオーバーライドする場合は <xref:System.Windows.Forms.Control.OnPaint%2A> 、通常、 <xref:System.Windows.Forms.Control.OnPaint%2A> 基本クラスのメソッドを呼び出して、登録されているデリゲートがイベントを受け取るようにする必要があり <xref:System.Windows.Forms.Control.Paint> ます。 ただし、画面全体を描画するコントロールでは、基本クラスのを呼び出さないでください。これにより、ちらつきが発生 <xref:System.Windows.Forms.Control.OnPaint%2A> します。 イベントをオーバーライドする例については、 <xref:System.Windows.Forms.Control.OnPaint%2A> 「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。  
  
> [!NOTE]
> コントロールから直接呼び出すのでは <xref:System.Windows.Forms.Control.OnPaint%2A> なく、 <xref:System.Windows.Forms.Control.Invalidate%2A> (から継承され <xref:System.Windows.Forms.Control> た) メソッドまたはを呼び出す他のメソッドを呼び出し <xref:System.Windows.Forms.Control.Invalidate%2A> ます。 <xref:System.Windows.Forms.Control.Invalidate%2A>メソッドが呼び出さ <xref:System.Windows.Forms.Control.OnPaint%2A> れます。 <xref:System.Windows.Forms.Control.Invalidate%2A>メソッドはオーバーロードされており、に指定された引数によっては、 <xref:System.Windows.Forms.Control.Invalidate%2A> `e` コントロールが画面領域の一部またはすべてを再描画します。  
  
 基底クラスは、 <xref:System.Windows.Forms.Control> 描画に便利な別のメソッド (メソッド) を定義し <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ます。  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ウィンドウの背景 (およびその図形) を描画し、高速であることを保証し <xref:System.Windows.Forms.Control.OnPaint%2A> ます。個々の描画要求は、再 <xref:System.Windows.Forms.Control.Paint> 描画する必要があるすべての領域を対象とした1つのイベントに結合されるため、詳細が描画され、速度が低下することがあります。 たとえば、 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> コントロールのグラデーションカラーの背景を描画する必要がある場合は、を呼び出すことができます。  
  
 に <xref:System.Windows.Forms.Control.OnPaintBackground%2A> はイベントのような用語があり、メソッドと同じ引数を取り `OnPaint` <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ますが、は true のイベントメソッドではありません。 イベントは存在せず `PaintBackground` 、 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> イベントデリゲートを呼び出しません。 メソッドをオーバーライドする場合 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 、派生クラスは <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 基底クラスのメソッドを呼び出す必要がありません。  
  
## <a name="gdi-basics"></a>GDI + の基礎  

 <xref:System.Drawing.Graphics>クラスには、円、三角形、円弧、楕円などのさまざまな図形を描画するためのメソッドと、テキストを表示するためのメソッドが用意されています。 <xref:System.Drawing?displayProperty=nameWithType>名前空間とその副名前空間には、図形 (円、四角形、円弧など)、色、フォント、ブラシなどのグラフィックス要素をカプセル化するクラスが含まれています。 GDI の詳細については、「 [マネージグラフィックスクラスの使用](../advanced/using-managed-graphics-classes.md)」を参照してください。 GDI の基本事項については、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」でも説明しています。  
  
## <a name="geometry-of-the-drawing-region"></a>描画領域のジオメトリ  

 <xref:System.Windows.Forms.Control.ClientRectangle%2A>コントロールのプロパティは、ユーザーの画面上のコントロールで使用できる四角形の領域を指定し <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ます。また、のプロパティは、実際に <xref:System.Windows.Forms.PaintEventArgs> 描画される領域を指定します。 (描画は、 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 引数としてインスタンスを受け取るイベントメソッドで行われることに注意してください)。 コントロールは、コントロールの表示の小さいセクションが変更された場合のように、使用可能な領域の一部だけを描画する必要がある場合があります。 このような状況では、コントロール開発者は、描画する実際の四角形を計算してに渡す必要があり <xref:System.Windows.Forms.Control.Invalidate%2A> ます。 <xref:System.Windows.Forms.Control.Invalidate%2A>引数としてまたはを受け取るのオーバーロードされたバージョンは、 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Region> その引数を使用してプロパティを生成し <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Windows.Forms.PaintEventArgs> ます。  
  
 次のコードフラグメントは、カスタムコントロールが四角形の領域を計算して描画する方法を示して `FlashTrackBar` います。 変数は、 `client` プロパティを表し <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ます。 完全なサンプルについては、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>グラフィックスリソースの解放  

 グラフィックスオブジェクトは、システムリソースを使用するため、コストが高くなります。 このようなオブジェクトには <xref:System.Drawing.Graphics?displayProperty=nameWithType> 、クラスのインスタンスだけ <xref:System.Drawing.Brush?displayProperty=nameWithType> でなく、、、 <xref:System.Drawing.Pen?displayProperty=nameWithType> およびその他のグラフィックスクラスのインスタンスが含まれます。 グラフィックスリソースは、必要なときにのみ作成し、使用が終了したらすぐにリリースすることが重要です。 インターフェイスを実装する型を作成する場合は <xref:System.IDisposable> 、 <xref:System.IDisposable.Dispose%2A> リソースを解放するために、メソッドの使用が終了したときにメソッドを呼び出します。  
  
 次のコードフラグメントは、 `FlashTrackBar` カスタムコントロールがリソースを作成および解放する方法を示して <xref:System.Drawing.Brush> います。 完全なソースコードについては、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>関連項目

- [方法: 進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)
