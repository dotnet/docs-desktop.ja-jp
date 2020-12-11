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
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="a224d-102">方法: バッファリングされたグラフィックスを手動で管理する</span><span class="sxs-lookup"><span data-stu-id="a224d-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="a224d-103">より高度なダブルバッファリングのシナリオでは、.NET Framework クラスを使用して、独自のダブルバッファリングロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="a224d-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="a224d-104">個々のグラフィックスバッファーの割り当てと管理を行うクラスは、 <xref:System.Drawing.BufferedGraphicsContext> クラスです。</span><span class="sxs-lookup"><span data-stu-id="a224d-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="a224d-105">すべてのアプリケーションには <xref:System.Drawing.BufferedGraphicsContext> 、そのアプリケーションのすべての既定のダブルバッファリングを管理する独自の既定値があります。</span><span class="sxs-lookup"><span data-stu-id="a224d-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="a224d-106">このインスタンスへの参照を取得するには、を呼び出し <xref:System.Drawing.BufferedGraphicsManager.Current%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a224d-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="a224d-107">既定の BufferedGraphicsContext への参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="a224d-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="a224d-108">次の <xref:System.Drawing.BufferedGraphicsManager.Current%2A> コード例に示すように、プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a224d-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="a224d-109">`Dispose` <xref:System.Drawing.BufferedGraphicsContext> クラスから受け取る参照に対してメソッドを呼び出す必要はありません <xref:System.Drawing.BufferedGraphicsManager> 。</span><span class="sxs-lookup"><span data-stu-id="a224d-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="a224d-110">は、 <xref:System.Drawing.BufferedGraphicsManager> 既定のインスタンスのメモリ割り当てと分布をすべて処理し <xref:System.Drawing.BufferedGraphicsContext> ます。</span><span class="sxs-lookup"><span data-stu-id="a224d-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="a224d-111">アニメーションなどのグラフィックを多用するアプリケーションの場合は、ではなく専用のを使用して、パフォーマンスを向上させることができ <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager> ます。</span><span class="sxs-lookup"><span data-stu-id="a224d-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="a224d-112">これにより、アプリケーションに関連付けられている他のすべてのバッファリングされたグラフィックスを管理する際のパフォーマンスオーバーヘッドを発生させずに、グラフィックスバッファーを個別に作成して管理できます。ただし、アプリケーションで使用されるメモリの方が多くなります。</span><span class="sxs-lookup"><span data-stu-id="a224d-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="a224d-113">専用の BufferedGraphicsContext を作成するには</span><span class="sxs-lookup"><span data-stu-id="a224d-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="a224d-114"><xref:System.Drawing.BufferedGraphicsContext>次のコード例に示すように、クラスの新しいインスタンスを宣言して作成します。</span><span class="sxs-lookup"><span data-stu-id="a224d-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="a224d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a224d-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="a224d-116">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="a224d-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="a224d-117">方法: バッファリングされたグラフィックスを手動で描画する</span><span class="sxs-lookup"><span data-stu-id="a224d-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
