---
title: ダブル バッファリングされたグラフィックス
ms.date: 03/30/2017
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
ms.openlocfilehash: 20ec03e6b84110f7ea00c134dc18b23f233c5f58
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980092"
---
# <a name="double-buffered-graphics"></a>ダブル バッファリングされたグラフィックス
グラフィックスをプログラミングするときは、ちらつきが一般的な問題になります。 複数の複雑な描画操作を必要とするグラフィックス操作を実行すると、描画されたイメージがちらつきなどによって適切に表示されないことがあります。 このような問題に対処するために、.NET Framework では、ダブル バッファリングを利用できます。  
  
 ダブル バッファリングでは、メモリ バッファーを使用して、複数の描画操作に関連するちらつきの問題に対処します。 ダブル バッファリングを有効にすると、すべての描画操作が画面上の描画サーフェイスではなく、最初にメモリ バッファーに描画されます。 描画操作がすべて完了すると、メモリ バッファーが、関連付けられている描画サーフェイスに直接コピーされます。 画面上で実行されるグラフィックス操作は 1 つだけなので、複雑な描画操作に関連するイメージのちらつきが解消されます。  
  
## <a name="default-double-buffering"></a>既定のダブル バッファリング  
 アプリケーションでダブル バッファリングを使用するには、.NET Framework に用意されている、フォームやコントロールに対する既定のダブル バッファリングを使用するのが最も簡単です。 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>プロパティをに設定する `true` か、またはメソッドを使用して、Windows フォームおよび作成された Windows コントロールの既定のダブルバッファリングを有効にすることができ <xref:System.Windows.Forms.Control.SetStyle%2A> ます。 詳細については、「[方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)」を参照してください。  
  
## <a name="manually-managing-buffered-graphics"></a>バッファリングされたグラフィックスの手動管理  
 アニメーションや高度なメモリ管理など、より高度なダブル バッファリングのシナリオでは、.NET Framework クラスを使用して独自のダブル バッファリング ロジックを実装できます。 個々のグラフィックスバッファーの割り当てと管理を行うクラスは、 <xref:System.Drawing.BufferedGraphicsContext> クラスです。 すべてのアプリケーションドメインには <xref:System.Drawing.BufferedGraphicsContext> 、そのアプリケーションのすべての既定のダブルバッファリングを管理する独自の既定のインスタンスがあります。 ほとんどの場合、アプリケーションごとにアプリケーションドメインは1つしか存在しないため、通常はアプリケーションごとに1つの既定値が存在 <xref:System.Drawing.BufferedGraphicsContext> します。 既定 <xref:System.Drawing.BufferedGraphicsContext> のインスタンスは、クラスによって管理され <xref:System.Drawing.BufferedGraphicsManager> ます。 を呼び出すことによって、既定のインスタンスへの参照を取得でき <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager.Current%2A> ます。 専用のインスタンスを作成することもでき <xref:System.Drawing.BufferedGraphicsContext> ます。これにより、グラフィカルに使用するアプリケーションのパフォーマンスを向上させることができます。 インスタンスの作成方法については <xref:System.Drawing.BufferedGraphicsContext> 、「 [方法: バッファリングされたグラフィックスを手動で管理](how-to-manually-manage-buffered-graphics.md)する」を参照してください。  
  
## <a name="manually-displaying-buffered-graphics"></a>バッファリングされたグラフィックスの手動表示  
 クラスのインスタンスを使用し <xref:System.Drawing.BufferedGraphicsContext> て、 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType> クラスのインスタンスを返すを呼び出すことによって、グラフィックスバッファーを作成でき <xref:System.Drawing.BufferedGraphics> ます。 オブジェクトは、 <xref:System.Drawing.BufferedGraphics> フォームやコントロールなどのレンダリングサーフェイスに関連付けられているメモリバッファーを管理します。  
  
 インスタンス化されると、 <xref:System.Drawing.BufferedGraphics> クラスはメモリ内グラフィックスバッファーへのレンダリングを管理します。 メモリバッファーを <xref:System.Drawing.BufferedGraphics.Graphics%2A> 直接表すオブジェクトを公開するを使用して、メモリバッファーにグラフィックスをレンダリングでき <xref:System.Drawing.Graphics> ます。 <xref:System.Drawing.Graphics>描画サーフェイスを表すオブジェクトと同じように、このオブジェクトに描画することができ <xref:System.Drawing.Graphics> ます。 すべてのグラフィックスがバッファーに描画されたら、を使用して、 <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> バッファーの内容を画面上の描画サーフェイスにコピーできます。  
  
 クラスの使用方法の詳細については <xref:System.Drawing.BufferedGraphics> 、「バッファリングされた [グラフィックスを手動でレンダリング](how-to-manually-render-buffered-graphics.md)する」を参照してください。 グラフィックスの描画の詳細については、「[Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.BufferedGraphics>
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphicsManager>
- [方法: バッファリングされたグラフィックスを手動で描画する](how-to-manually-render-buffered-graphics.md)
- [方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)
- [方法: バッファリングされたグラフィックスを手動で管理する](how-to-manually-manage-buffered-graphics.md)
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
