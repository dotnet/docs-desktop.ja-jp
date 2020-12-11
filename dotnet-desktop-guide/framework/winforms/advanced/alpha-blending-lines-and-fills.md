---
title: アルファ ブレンドの直線と塗りつぶし
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974910"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="dee04-102">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="dee04-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="dee04-103">GDI + では、色はそれぞれアルファ、赤、緑、および青の8ビットを持つ32ビット値です。</span><span class="sxs-lookup"><span data-stu-id="dee04-103">In GDI+, a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="dee04-104">アルファ値は、色の透明度 (色を背景色とブレンドする範囲) を示します。</span><span class="sxs-lookup"><span data-stu-id="dee04-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="dee04-105">アルファ値は 0 ~ 255 の範囲です。0は完全に透明な色を表し、255は完全に不透明な色を表します。</span><span class="sxs-lookup"><span data-stu-id="dee04-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="dee04-106">アルファブレンドは、ソースと背景のカラーデータのピクセル単位のブレンドです。</span><span class="sxs-lookup"><span data-stu-id="dee04-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="dee04-107">特定のソース色の3つの各コンポーネント (赤、緑、青) は、次の式に従って、背景色の対応する要素とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="dee04-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="dee04-108">displayColor = sourceColor × alpha/255 + backgroundColor × (255 – alpha)/255</span><span class="sxs-lookup"><span data-stu-id="dee04-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="dee04-109">たとえば、ソースの色の赤の部分が150で、背景色の赤の要素が100であるとします。</span><span class="sxs-lookup"><span data-stu-id="dee04-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="dee04-110">アルファ値が200の場合、結果の色の赤の成分は次のように計算されます。</span><span class="sxs-lookup"><span data-stu-id="dee04-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="dee04-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="dee04-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dee04-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dee04-112">In This Section</span></span>  
 [<span data-ttu-id="dee04-113">方法: 不透明な直線および半透明な直線を描画する</span><span class="sxs-lookup"><span data-stu-id="dee04-113">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="dee04-114">アルファブレンドされた直線を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dee04-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="dee04-115">方法: 不透明ブラシおよび半透明ブラシを使用して描画する</span><span class="sxs-lookup"><span data-stu-id="dee04-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="dee04-116">ブラシを使用してアルファブレンドを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dee04-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="dee04-117">方法: 複合モードを使用してアルファ ブレンドを制御する</span><span class="sxs-lookup"><span data-stu-id="dee04-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="dee04-118">を使用してアルファブレンドを制御する方法について説明し <xref:System.Drawing.Drawing2D.CompositingMode> ます。</span><span class="sxs-lookup"><span data-stu-id="dee04-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="dee04-119">方法: カラー行列を使用してイメージのアルファ値を設定する</span><span class="sxs-lookup"><span data-stu-id="dee04-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="dee04-120">オブジェクトを使用してアルファブレンドを制御する方法について説明 <xref:System.Drawing.Imaging.ColorMatrix> します。</span><span class="sxs-lookup"><span data-stu-id="dee04-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
