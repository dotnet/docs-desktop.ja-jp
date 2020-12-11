---
title: '方法: 純色ブラシを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974830"
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="c2655-102">方法: 純色ブラシを作成する</span><span class="sxs-lookup"><span data-stu-id="c2655-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="c2655-103">この例では、 <xref:System.Drawing.SolidBrush> オブジェクトが図形を塗りつぶすために使用できるオブジェクトを作成し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="c2655-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2655-104">例</span><span class="sxs-lookup"><span data-stu-id="c2655-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c2655-105">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="c2655-105">Robust Programming</span></span>  
 <span data-ttu-id="c2655-106">これらの使用が完了したら、 <xref:System.IDisposable.Dispose%2A> ブラシオブジェクトなどのシステムリソースを消費するオブジェクトに対してを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2655-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2655-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2655-107">See also</span></span>

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="c2655-108">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="c2655-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c2655-109">GDI+ でのブラシと塗りつぶされた図形</span><span class="sxs-lookup"><span data-stu-id="c2655-109">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
- [<span data-ttu-id="c2655-110">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="c2655-110">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
