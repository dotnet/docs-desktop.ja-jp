---
title: '方法: MatrixTransform を使用してカスタム変換を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984544"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="85e06-102">方法: MatrixTransform を使用してカスタム変換を作成する</span><span class="sxs-lookup"><span data-stu-id="85e06-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="85e06-103">この例では、<xref:System.Windows.Media.MatrixTransform> を使用して、<xref:System.Windows.Controls.Button> の位置、伸縮、および傾斜を変換 (移動) する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85e06-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85e06-104"><xref:System.Windows.Media.MatrixTransform> クラスを使用して、<xref:System.Windows.Media.RotateTransform> クラス、<xref:System.Windows.Media.SkewTransform> クラス、<xref:System.Windows.Media.ScaleTransform> クラス、または <xref:System.Windows.Media.TranslateTransform> クラスによって指定されないカスタム変換を作成します。</span><span class="sxs-lookup"><span data-stu-id="85e06-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85e06-105">例</span><span class="sxs-lookup"><span data-stu-id="85e06-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="85e06-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="85e06-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="85e06-107">変換の概要</span><span class="sxs-lookup"><span data-stu-id="85e06-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="85e06-108">方法トピック</span><span class="sxs-lookup"><span data-stu-id="85e06-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="85e06-109">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="85e06-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
