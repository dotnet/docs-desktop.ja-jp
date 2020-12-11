---
title: 曲線の作成と描画
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975049"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="150b0-102">曲線の作成と描画</span><span class="sxs-lookup"><span data-stu-id="150b0-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="150b0-103">GDI + では、楕円、円弧、カーディナルスプライン、ベジエスプラインなど、いくつかの種類の曲線がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="150b0-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="150b0-104">楕円は、外接する四角形によって定義されます。弧は、開始角度とスイープ角度で定義された楕円の一部です。</span><span class="sxs-lookup"><span data-stu-id="150b0-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="150b0-105">カーディナルスプラインは、点の配列とテンションパラメーターによって定義されます。曲線は配列内の各点をスムーズに通過し、テンションパラメーターは曲線のベンド方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="150b0-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="150b0-106">ベジエスプラインは、2つのエンドポイントと2つの制御点によって定義されています。曲線はコントロールポイントを通過しませんが、曲線があるエンドポイントから別のエンドポイントに到達すると、制御点が方向とベンドに影響します。</span><span class="sxs-lookup"><span data-stu-id="150b0-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="150b0-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="150b0-107">In This Section</span></span>  
 [<span data-ttu-id="150b0-108">方法: カーディナル スプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="150b0-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="150b0-109">カーディナルスプラインとその描画方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="150b0-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="150b0-110">方法: 1 本のベジエ スプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="150b0-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="150b0-111">ベジエスプラインとその描画方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="150b0-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="150b0-112">方法: 一連のベジエ スプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="150b0-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="150b0-113">複数のベジエスプラインを順番に描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="150b0-113">Explains how to draw several Bézier splines in sequence.</span></span>
