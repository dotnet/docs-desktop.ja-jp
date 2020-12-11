---
title: ペンを使用した直線と図形の描画
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: d20b4e47c9f8a5dd7a144e6ebb3151d3ab65a800
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975234"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="d447b-102">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="d447b-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="d447b-103">GDI + オブジェクトを使用し `Pen` て、直線セグメント、曲線、および図形のアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="d447b-103">Use GDI+ `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="d447b-104">このセクションでは *、行セグメント* のみを意味するように指定されている場合を除き、これらのいずれかを表します。</span><span class="sxs-lookup"><span data-stu-id="d447b-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="d447b-105">ペンのプロパティを設定して、そのペンで描画される線の色、幅、配置、およびスタイルを制御します。</span><span class="sxs-lookup"><span data-stu-id="d447b-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d447b-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d447b-106">In This Section</span></span>  
 [<span data-ttu-id="d447b-107">方法: ペンを使用して線を描画する</span><span class="sxs-lookup"><span data-stu-id="d447b-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="d447b-108">線を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d447b-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="d447b-109">方法: ペンを使用して四角形を描画する</span><span class="sxs-lookup"><span data-stu-id="d447b-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="d447b-110">四角形を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d447b-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="d447b-111">方法: ペンの幅と配置を設定する</span><span class="sxs-lookup"><span data-stu-id="d447b-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="d447b-112">オブジェクトの幅と配置を変更する方法について説明し `Pen` ます。</span><span class="sxs-lookup"><span data-stu-id="d447b-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="d447b-113">方法: ライン キャップを使用した直線を描画する</span><span class="sxs-lookup"><span data-stu-id="d447b-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="d447b-114">線を描画するときに、端のキャップを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d447b-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="d447b-115">方法: 直線を接合する</span><span class="sxs-lookup"><span data-stu-id="d447b-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="d447b-116">2つの線を結合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d447b-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="d447b-117">方法: カスタム破線を描画する</span><span class="sxs-lookup"><span data-stu-id="d447b-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="d447b-118">破線を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d447b-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="d447b-119">方法: テクスチャを使用して塗りつぶした直線を描画する</span><span class="sxs-lookup"><span data-stu-id="d447b-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="d447b-120">テクスチャで塗りつぶされた線を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d447b-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d447b-121">リファレンス</span><span class="sxs-lookup"><span data-stu-id="d447b-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="d447b-122">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d447b-122">Describes this class and has links to all its members.</span></span>
