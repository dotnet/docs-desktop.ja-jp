---
title: コントロールのカスタム ペインティング
description: Windows フォーム用の .NET の OnPaint メソッドと Paint イベントを使用して、コントロールの外観をカスタマイズする方法について説明します。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
f1_keywords:
- OnPaint
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 8d9775c02addb68cc962cdc2e4bf2d1baa6ab2a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942278"
---
# <a name="painting-and-drawing-on-controls-windows-forms-net"></a>コントロールのペインティングと描画 (.NET 用の Windows フォーム)

コントロールのカスタム ペインティングは、Windows フォームによって簡単に実行できる多数の複雑なタスクの 1 つです。 カスタム コントロールを作成する場合、コントロールのグラフィカルな外観を処理するために使用できる多くのオプションがあります。 [カスタム コントロール](custom.md#custom-controls)、つまり <xref:System.Windows.Forms.Control> から継承するコントロールを作成する場合は、そのグラフィカル表現をレンダリングするコードを用意する必要があります。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

[複合コントロール](custom.md#composite-controls)、つまり <xref:System.Windows.Forms.UserControl> または既存の Windows フォーム コントロールのいずれかを継承するコントロールを作成する場合は、標準のグラフィカル表現をオーバーライドし、独自のグラフィックス コードを提供することができます。

新しいコントロールを作成せずに既存のコントロールのカスタム レンダリングを提供する場合は、オプションがいっそう限られたものになります。 ただし、それでもコントロールとアプリケーションに対して、広い範囲のグラフィカルの可能性があります。

コントロールのレンダリングには、次の要素が関係します。

- 基底クラス <xref:System.Windows.Forms.Control?displayProperty=nameWithType> によって提供される描画機能。
- GDI グラフィックス ライブラリの必須要素。
- 描画領域のジオメトリ。
- グラフィックス リソースを解放する手順。

## <a name="drawing-provided-by-control"></a>コントロールによって提供される描画

基底クラス <xref:System.Windows.Forms.Control> の <xref:System.Windows.Forms.Control.Paint> イベントを通じて描画機能が提供されます。 表示を更新する必要があるたびに、コントロールによって <xref:System.Windows.Forms.Control.Paint> イベントが生成されます。 .NET でのイベントの詳細については、「[イベントの処理と発生](/dotnet/standard/events/index)」を参照してください。

<xref:System.Windows.Forms.Control.Paint> イベントのイベント データ クラスである <xref:System.Windows.Forms.PaintEventArgs> により、コントロールの描画に必要なデータである、グラフィックス オブジェクトへのハンドルと、描画する領域を表す四角形が保持されます。

```csharp
public class PaintEventArgs : EventArgs, IDisposable
{

    public System.Drawing.Rectangle ClipRectangle {get;}
    public System.Drawing.Graphics Graphics {get;}

    // Other properties and methods.
}
```

```vb
Public Class PaintEventArgs
    Inherits EventArgs
    Implements IDisposable

    Public ReadOnly Property ClipRectangle As System.Drawing.Rectangle
    Public ReadOnly Property Graphics As System.Drawing.Graphics

    ' Other properties and methods.
End Class
```

<xref:System.Drawing.Graphics> は、描画機能をカプセル化するマネージド クラスです (この記事の GDI に関する説明で後述します)。 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> は <xref:System.Drawing.Rectangle> 構造体のインスタンスであり、コントロールで描画できる領域を定義します。 コントロール開発者は、コントロールの <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティを使用して、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> を計算できます (この記事のジオメトリに関する説明で後述します)。

### <a name="onpaint"></a>OnPaint

コントロールは <xref:System.Windows.Forms.Control> から継承する <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドすることにより、レンダリング ロジックを提供する必要があります。 <xref:System.Windows.Forms.Control.OnPaint%2A> は、渡された <xref:System.Windows.Forms.PaintEventArgs> インスタンスの <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> および <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティを通じて、グラフィックス オブジェクトと描画対象の四角形にアクセスします。

次のコードでは、`System.Drawing` 名前空間を使用しています。

:::code language="csharp" source="./snippets/custom-painting-drawing/cs/UserControl1.cs" id="OnPaintMethod":::

:::code language="vb" source="./snippets/custom-painting-drawing/vb/UserControl1.vb" id="OnPaintMethod":::

基底クラス <xref:System.Windows.Forms.Control> の <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドによって描画機能は実装されず、<xref:System.Windows.Forms.Control.Paint> イベントに登録されているイベント デリゲートを単に呼び出すだけです。 <xref:System.Windows.Forms.Control.OnPaint%2A> をオーバーライドするときは、登録されているデリゲートで <xref:System.Windows.Forms.Control.Paint> イベントを受け取ることができるように、通常、基底クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドを呼び出す必要があります。 ただし、画面全体を描画するコントロールの場合は、基底クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> を呼び出すことはできません。これによって、ちらつきが生じるためです。

> [!NOTE]
> コントロールから直接 <xref:System.Windows.Forms.Control.OnPaint%2A> を呼び出さないでください。代わりに、<xref:System.Windows.Forms.Control.Invalidate%2A> メソッド (<xref:System.Windows.Forms.Control> から継承)、または <xref:System.Windows.Forms.Control.Invalidate%2A> を呼び出す他のメソッドを呼び出します。 <xref:System.Windows.Forms.Control.Invalidate%2A> メソッドによって、<xref:System.Windows.Forms.Control.OnPaint%2A> が呼び出されます。 <xref:System.Windows.Forms.Control.Invalidate%2A> メソッドはオーバーロードされ、<xref:System.Windows.Forms.Control.Invalidate%2A> `e` に指定された引数に応じて、その画面領域の一部または全体が再描画されます。

コントロールが最初に描画されるときと、更新されるたびに、コントロールの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドのコードが実行されます。 サイズが変更されるたびにコントロールが確実に再描画されるようにするには、コントロールのコンストラクターに次の行を追加します。

```csharp
SetStyle(ControlStyles.ResizeRedraw, true);
```

```vb
SetStyle(ControlStyles.ResizeRedraw, True)
```

### <a name="onpaintbackground"></a>OnPaintBackground

基底クラス <xref:System.Windows.Forms.Control> により、描画に便利なもう 1 つのメソッド <xref:System.Windows.Forms.Control.OnPaintBackground%2A> が定義されています。

```csharp
protected virtual void OnPaintBackground(PaintEventArgs e);
```

```vb
Protected Overridable Sub OnPaintBackground(e As PaintEventArgs)
```

<xref:System.Windows.Forms.Control.OnPaintBackground%2A> を使用すると、ウィンドウの背景 (およびそのシェイプ) が描画され、高速な処理が保証されます。一方、<xref:System.Windows.Forms.Control.OnPaint%2A> を使用すると、細部が描画され、個々の描画要求が、再描画の必要なすべての領域をカバーする 1 つの <xref:System.Windows.Forms.Control.Paint> イベントに結合されるため、処理が遅くなる場合があります。 たとえば、コントロールのグラデーション カラーの背景を描画する必要がある場合は、<xref:System.Windows.Forms.Control.OnPaintBackground%2A> を呼び出す必要がある場合があります。

<xref:System.Windows.Forms.Control.OnPaintBackground%2A> にはイベントのような命名法があり、`OnPaint` メソッドと同じ引数を受け取りますが、`OnPaintBackground` は本当のイベント メソッドではありません。 `PaintBackground` イベントは存在せず、`OnPaintBackground` でイベント デリゲートは呼び出されません。 `OnPaintBackground` メソッドをオーバーライドするとき、派生クラスで基底クラスの `OnPaintBackground` メソッドを呼び出す必要はありません。

## <a name="gdi-basics"></a>GDI+ の基礎

<xref:System.Drawing.Graphics> クラスには、円、三角形、円弧、楕円などのさまざまなシェイプを描画するためのメソッドと、テキストを表示するためのメソッドが用意されています。 <xref:System.Drawing?displayProperty=nameWithType> 名前空間には、シェイプ (円、四角形、円弧など)、色、フォント、ブラシなどのグラフィックス要素をカプセル化する名前空間とクラスが含まれています。<!-- TODO  For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).-->

## <a name="geometry-of-the-drawing-region"></a>描画領域のジオメトリ

コントロールの <xref:System.Windows.Forms.Control.ClientRectangle%2A> プロパティにより、ユーザーの画面上でコントロールが使用できる四角形の領域が指定されています。一方、<xref:System.Windows.Forms.PaintEventArgs> の <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティにより、描画される領域が指定されます。 コントロールの表示の小さいセクションが変更された場合のように、コントロールで使用可能な領域の一部だけを描画することが必要になる場合があります。 そのような状況では、コントロール開発者は、実際に描画する四角形を計算し、それを <xref:System.Windows.Forms.Control.Invalidate%2A> に渡す必要があります。 引数として <xref:System.Drawing.Rectangle> または <xref:System.Drawing.Region> を受け取る <xref:System.Windows.Forms.Control.Invalidate%2A> のオーバーロードされたバージョンにより、その引数を使用して、<xref:System.Windows.Forms.PaintEventArgs> の <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティが生成されます。

## <a name="freeing-graphics-resources"></a>グラフィックス リソースの解放

グラフィックス オブジェクトは、システム リソースを使用するため、コストが高くなります。 そのようなオブジェクトには、<xref:System.Drawing.Graphics?displayProperty=nameWithType> クラスのインスタンスと、<xref:System.Drawing.Brush?displayProperty=nameWithType>、<xref:System.Drawing.Pen?displayProperty=nameWithType>、およびその他のグラフィックス クラスのインスタンスが含まれます。 必要なときにだけグラフィックス リソースを作成し、使い終わったらすぐに解放することが重要です。 <xref:System.IDisposable> インターフェイスが実装されている型のインスタンスを作成する場合は、終了したらその <xref:System.IDisposable.Dispose%2A> メソッドを呼び出してリソースを解放します。

## <a name="see-also"></a>関連項目

- [カスタム コントロールの種類](custom.md)
