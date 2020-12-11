---
title: '方法: RectangleGeometry の角に丸みを付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984056"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="ea92d-102">方法: RectangleGeometry の角に丸みを付ける</span><span class="sxs-lookup"><span data-stu-id="ea92d-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="ea92d-103"><xref:System.Windows.Media.RectangleGeometry> の角を丸めるには、その <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> と <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> のプロパティを 0 より大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea92d-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="ea92d-104">値が大きいほど、四角形の角が丸くなります。</span><span class="sxs-lookup"><span data-stu-id="ea92d-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea92d-105">例</span><span class="sxs-lookup"><span data-stu-id="ea92d-105">Example</span></span>  
 <span data-ttu-id="ea92d-106">次の例は <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> と <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> の設定が異なるいくつかの <xref:System.Windows.Media.RectangleGeometry> オブジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="ea92d-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="ea92d-107"><xref:System.Windows.Media.RectangleGeometry> オブジェクトは <xref:System.Windows.Shapes.Path> 要素を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea92d-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="ea92d-108">![RadiusX&#47;RadiusY 設定が異なる四角形](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="ea92d-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="ea92d-109">角が丸い四角形</span><span class="sxs-lookup"><span data-stu-id="ea92d-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea92d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea92d-110">See also</span></span>

- [<span data-ttu-id="ea92d-111">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="ea92d-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="ea92d-112">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="ea92d-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="ea92d-113">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="ea92d-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
