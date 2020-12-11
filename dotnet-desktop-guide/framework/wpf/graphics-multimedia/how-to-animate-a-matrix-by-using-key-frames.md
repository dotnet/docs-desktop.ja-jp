---
title: '方法: キー フレームを使用して行列をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984147"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="8aeb0-102">方法: キー フレームを使用して行列をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="8aeb0-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="8aeb0-103">この例では、キー フレームを使用して <xref:System.Windows.Media.MatrixTransform> の <xref:System.Windows.Media.MatrixTransform.Matrix%2A> プロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aeb0-104">例</span><span class="sxs-lookup"><span data-stu-id="8aeb0-104">Example</span></span>  
 <span data-ttu-id="8aeb0-105">次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> クラスを使用して、<xref:System.Windows.Media.MatrixTransform> の <xref:System.Windows.Media.MatrixTransform.Matrix%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="8aeb0-106">この例では、<xref:System.Windows.Media.MatrixTransform> オブジェクトを使用して、<xref:System.Windows.Controls.Button> の外観と位置を変換します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="8aeb0-107">このアニメーションでは、<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> クラスを使用して 2 つのキー フレームを作成し、それらを使用して次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="8aeb0-108">最初の 0.2 秒間で、最初の <xref:System.Windows.Media.Matrix> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="8aeb0-109">この例では、<xref:System.Windows.Media.Matrix> の <xref:System.Windows.Media.Matrix.M11%2A> プロパティと <xref:System.Windows.Media.Matrix.M12%2A> プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="8aeb0-110">この変更により、ボタンが引き伸ばされて、傾斜します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="8aeb0-111">また、この例では、ボタンの位置が変更するように、<xref:System.Windows.Media.Matrix.OffsetX%2A> プロパティと <xref:System.Windows.Media.Matrix.OffsetY%2A> プロパティも変更されます。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="8aeb0-112">2番目の <xref:System.Windows.Media.Matrix> を 1.0 秒でアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="8aeb0-113">ボタンは別の位置に移動しますが、ボタンの傾斜や引き伸ばしは行われなくなります。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="8aeb0-114">アニメーションを無限に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8aeb0-115"><xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> オブジェクトから派生するキー フレームによって、ある値から次の値への突然の変化が作成されます。つまり、アニメーションの動きがぎくしゃくします。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="8aeb0-116">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aeb0-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aeb0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aeb0-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="8aeb0-118">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="8aeb0-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="8aeb0-119">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="8aeb0-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
