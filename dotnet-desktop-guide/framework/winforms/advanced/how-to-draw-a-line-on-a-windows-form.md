---
title: '方法: Windows フォームに直線を描画する'
description: 描画イベントを処理してフォーム上に線を描画し、PaintEventArgs の Graphics プロパティを使用して描画を実行する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981867"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="b8ca3-103">方法: Windows フォームに直線を描画する</span><span class="sxs-lookup"><span data-stu-id="b8ca3-103">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="b8ca3-104">この例では、フォーム上に線を描画します。</span><span class="sxs-lookup"><span data-stu-id="b8ca3-104">This example draws a line on a form.</span></span> <span data-ttu-id="b8ca3-105">通常、フォームで描画する場合は、フォームのイベントを処理  <xref:System.Windows.Forms.Control.Paint> し、のプロパティを使用して描画を実行します。 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs> 次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8ca3-105">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8ca3-106">例</span><span class="sxs-lookup"><span data-stu-id="b8ca3-106">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8ca3-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b8ca3-107">Compiling the Code</span></span>  
 <span data-ttu-id="b8ca3-108">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b8ca3-108">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b8ca3-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="b8ca3-109">Robust Programming</span></span>  
 <span data-ttu-id="b8ca3-110"><xref:System.IDisposable.Dispose%2A>オブジェクトなどのシステムリソースを消費するオブジェクトに対しては、常にを呼び出す必要があり <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="b8ca3-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ca3-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8ca3-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="b8ca3-112">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="b8ca3-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="b8ca3-113">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="b8ca3-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="b8ca3-114">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="b8ca3-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
