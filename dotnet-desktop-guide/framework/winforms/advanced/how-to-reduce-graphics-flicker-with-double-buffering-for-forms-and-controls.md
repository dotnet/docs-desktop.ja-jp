---
title: '方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する'
description: Windows フォームのダブルバッファリングを使用してグラフィックスのちらつきを軽減する方法と、コントロールを使用して描画操作に関連するちらつきの問題に対処する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981292"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="e2f84-103">方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する</span><span class="sxs-lookup"><span data-stu-id="e2f84-103">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="e2f84-104">ダブル バッファリングでは、メモリ バッファーを使用して、複数の描画操作に関連するちらつきの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="e2f84-104">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="e2f84-105">ダブル バッファリングを有効にすると、すべての描画操作が画面上の描画サーフェイスではなく、最初にメモリ バッファーに描画されます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-105">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="e2f84-106">描画操作がすべて完了すると、メモリ バッファーが、関連付けられている描画サーフェイスに直接コピーされます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-106">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="e2f84-107">画面上で実行されるグラフィックス操作は1つだけであるため、複雑な描画操作に関連付けられているイメージのちらつきが解消されます。ほとんどのアプリケーションでは、.NET Framework によって提供される既定のダブルバッファリングによって最適な結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-107">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the .NET Framework will provide the best results.</span></span> <span data-ttu-id="e2f84-108">標準 Windows フォームコントロールは、既定ではダブルバッファリングされます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-108">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="e2f84-109">フォームと作成されたコントロールでの既定のダブルバッファリングは、次の2つの方法で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-109">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="e2f84-110">プロパティをに設定するか、 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> `true` メソッドを呼び出してフラグをに設定することができ <xref:System.Windows.Forms.Control.SetStyle%2A> <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-110">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="e2f84-111">どちらの方法でも、フォームまたはコントロールの既定のダブルバッファリングが有効になり、ちらつきなしのグラフィックスレンダリングが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-111">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="e2f84-112">メソッドの呼び出し <xref:System.Windows.Forms.Control.SetStyle%2A> は、すべてのレンダリングコードを記述したカスタムコントロールに対してのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-112">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="e2f84-113">アニメーションや高度なメモリ管理などのより高度なダブルバッファリングシナリオでは、独自のダブルバッファリングロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="e2f84-113">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="e2f84-114">詳細については、「 [方法: バッファリングされたグラフィックスを手動で管理する](how-to-manually-manage-buffered-graphics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2f84-114">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="e2f84-115">ちらつきを軽減するには</span><span class="sxs-lookup"><span data-stu-id="e2f84-115">To reduce flicker</span></span>  
  
- <span data-ttu-id="e2f84-116"><xref:System.Windows.Forms.Control.DoubleBuffered%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="e2f84-116">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="e2f84-117">\- または</span><span class="sxs-lookup"><span data-stu-id="e2f84-117">\- or -</span></span>  
  
- <span data-ttu-id="e2f84-118">メソッドを呼び出して <xref:System.Windows.Forms.Control.SetStyle%2A> 、 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> フラグをに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="e2f84-118">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="e2f84-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2f84-119">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="e2f84-120">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="e2f84-120">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="e2f84-121">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="e2f84-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
