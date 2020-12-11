---
title: '方法: バッファリングされたグラフィックスを手動で管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981816"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>方法: バッファリングされたグラフィックスを手動で管理する
より高度なダブルバッファリングのシナリオでは、.NET Framework クラスを使用して、独自のダブルバッファリングロジックを実装できます。 個々のグラフィックスバッファーの割り当てと管理を行うクラスは、 <xref:System.Drawing.BufferedGraphicsContext> クラスです。 すべてのアプリケーションには <xref:System.Drawing.BufferedGraphicsContext> 、そのアプリケーションのすべての既定のダブルバッファリングを管理する独自の既定値があります。 このインスタンスへの参照を取得するには、を呼び出し <xref:System.Drawing.BufferedGraphicsManager.Current%2A> ます。  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>既定の BufferedGraphicsContext への参照を取得するには  
  
- 次の <xref:System.Drawing.BufferedGraphicsManager.Current%2A> コード例に示すように、プロパティを設定します。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > `Dispose` <xref:System.Drawing.BufferedGraphicsContext> クラスから受け取る参照に対してメソッドを呼び出す必要はありません <xref:System.Drawing.BufferedGraphicsManager> 。 は、 <xref:System.Drawing.BufferedGraphicsManager> 既定のインスタンスのメモリ割り当てと分布をすべて処理し <xref:System.Drawing.BufferedGraphicsContext> ます。  
  
     アニメーションなどのグラフィックを多用するアプリケーションの場合は、ではなく専用のを使用して、パフォーマンスを向上させることができ <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager> ます。 これにより、アプリケーションに関連付けられている他のすべてのバッファリングされたグラフィックスを管理する際のパフォーマンスオーバーヘッドを発生させずに、グラフィックスバッファーを個別に作成して管理できます。ただし、アプリケーションで使用されるメモリの方が多くなります。  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>専用の BufferedGraphicsContext を作成するには  
  
- <xref:System.Drawing.BufferedGraphicsContext>次のコード例に示すように、クラスの新しいインスタンスを宣言して作成します。  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.BufferedGraphicsContext>
- [ダブル バッファリングされたグラフィックス](double-buffered-graphics.md)
- [方法: バッファリングされたグラフィックスを手動で描画する](how-to-manually-render-buffered-graphics.md)
