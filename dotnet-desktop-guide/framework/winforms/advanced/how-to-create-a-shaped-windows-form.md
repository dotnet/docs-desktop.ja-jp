---
title: '方法: 成型された Windows フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 3c90e6d5d2613239e513f8ec30d67b58084cba5e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974834"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="43eb8-102">方法: 成型された Windows フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="43eb8-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="43eb8-103">この例では、フォームのサイズを変更する楕円図形をフォームに渡します。</span><span class="sxs-lookup"><span data-stu-id="43eb8-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43eb8-104">例</span><span class="sxs-lookup"><span data-stu-id="43eb8-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="43eb8-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="43eb8-105">Compiling the Code</span></span>  
 <span data-ttu-id="43eb8-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="43eb8-106">This example requires:</span></span>  
  
- <span data-ttu-id="43eb8-107"><xref:System.Windows.Forms> 名前空間と <xref:System.Drawing> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="43eb8-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="43eb8-108">この例では、メソッドをオーバーライドして、 <xref:System.Windows.Forms.Control.OnPaint%2A> フォームの形状を変更します。</span><span class="sxs-lookup"><span data-stu-id="43eb8-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="43eb8-109">このコードを使用するには、メソッドの宣言と、メソッド内の描画コードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="43eb8-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43eb8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="43eb8-110">See also</span></span>

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="43eb8-111">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="43eb8-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
