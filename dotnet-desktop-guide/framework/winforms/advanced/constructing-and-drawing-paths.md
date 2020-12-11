---
title: パスの作成および描画
ms.date: 03/30/2017
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
ms.openlocfilehash: a698b93aac29a0a7f5c959b29a3feb41eb447e8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974447"
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="0562d-102">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="0562d-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="0562d-103">パスとは、1つの単位として操作および描画できるグラフィックスプリミティブ (線、四角形、曲線、テキストなど) のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="0562d-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="0562d-104">パスは、開いているか閉じている *図形* に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="0562d-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="0562d-105">図形には、いくつかのプリミティブを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0562d-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="0562d-106">クラスのメソッドを呼び出すことによってパスを描画でき <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Graphics> ます。また、クラスのメソッドを呼び出すことによってパスを埋めることができ <xref:System.Drawing.Graphics.FillPath%2A> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="0562d-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0562d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0562d-107">In This Section</span></span>  
 [<span data-ttu-id="0562d-108">方法: 直線、曲線、および形状から図形を作成する</span><span class="sxs-lookup"><span data-stu-id="0562d-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="0562d-109">を使用して図形を作成する方法について説明し <xref:System.Drawing.Drawing2D.GraphicsPath> ます。</span><span class="sxs-lookup"><span data-stu-id="0562d-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="0562d-110">方法: 開いている図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="0562d-110">How to: Fill Open Figures</span></span>](how-to-fill-open-figures.md)  
 <span data-ttu-id="0562d-111">にデータを格納する方法について説明 <xref:System.Drawing.Drawing2D.GraphicsPath> します。</span><span class="sxs-lookup"><span data-stu-id="0562d-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="0562d-112">方法: 曲線のパスを直線に平坦化する</span><span class="sxs-lookup"><span data-stu-id="0562d-112">How to: Flatten a Curved Path into a Line</span></span>](how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="0562d-113">を平坦化する方法を示し <xref:System.Drawing.Drawing2D.GraphicsPath> ます。</span><span class="sxs-lookup"><span data-stu-id="0562d-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0562d-114">リファレンス</span><span class="sxs-lookup"><span data-stu-id="0562d-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="0562d-115">このクラスについて説明し、そのすべてのメンバーへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="0562d-115">Describes this class and contains links to all of its members.</span></span>
