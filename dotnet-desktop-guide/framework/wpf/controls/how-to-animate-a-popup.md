---
title: '方法: ポップアップをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984456"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="dd477-102">方法: ポップアップをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="dd477-102">How to: Animate a Popup</span></span>
<span data-ttu-id="dd477-103">この例では、<xref:System.Windows.Controls.Primitives.Popup> コントロールをアニメーション化する 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd477-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd477-104">例</span><span class="sxs-lookup"><span data-stu-id="dd477-104">Example</span></span>  
 <span data-ttu-id="dd477-105">次の例では、<xref:System.Windows.Controls.Primitives.PopupAnimation> プロパティが値 <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide> に設定されています。それにより、<xref:System.Windows.Controls.Primitives.Popup> は表示時、"スライドイン" します。</span><span class="sxs-lookup"><span data-stu-id="dd477-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="dd477-106"><xref:System.Windows.Controls.Primitives.Popup> を回転させるため、この例では、<xref:System.Windows.Controls.Primitives.Popup> の子要素である <xref:System.Windows.Controls.Canvas> で <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに <xref:System.Windows.Media.RotateTransform> が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="dd477-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="dd477-107">変換を正しく機能させるため、この例では、<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> プロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd477-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="dd477-108">また、<xref:System.Windows.Controls.Primitives.Popup> が回転するために十分な空間を <xref:System.Windows.Controls.Canvas> の <xref:System.Windows.FrameworkElement.Margin%2A> で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd477-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="dd477-109">次の例では、<xref:System.Windows.Controls.Button> のクリック時に発生する <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントによって、アニメーションを開始する <xref:System.Windows.Media.Animation.Storyboard> がトリガーされるしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="dd477-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="dd477-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd477-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="dd477-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="dd477-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="dd477-112">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="dd477-112">Popup Overview</span></span>](popup-overview.md)
