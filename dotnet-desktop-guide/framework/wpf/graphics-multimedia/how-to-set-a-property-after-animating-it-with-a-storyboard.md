---
title: '方法: ストーリーボードを使用してアニメーション化した後にプロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 593d3fcefe3bb81518d0886afde82f9a172874ba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983259"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="6732f-102">方法: ストーリーボードを使用してアニメーション化した後にプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="6732f-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="6732f-103">プロパティをアニメーション化した後に、その値を変更できないように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="6732f-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6732f-104">例</span><span class="sxs-lookup"><span data-stu-id="6732f-104">Example</span></span>  
 <span data-ttu-id="6732f-105">次の例では、<xref:System.Windows.Media.Animation.Storyboard> は <xref:System.Windows.Media.SolidColorBrush> の色をアニメーション化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6732f-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="6732f-106">ボタンをクリックすると、ストーリーボードがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="6732f-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="6732f-107"><xref:System.Windows.Media.Animation.Timeline.Completed> イベントは、<xref:System.Windows.Media.Animation.ColorAnimation> が完了したときにプログラムに通知されるように処理されます。</span><span class="sxs-lookup"><span data-stu-id="6732f-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="6732f-108">例</span><span class="sxs-lookup"><span data-stu-id="6732f-108">Example</span></span>  
 <span data-ttu-id="6732f-109"><xref:System.Windows.Media.Animation.ColorAnimation> が完了すると、プログラムはブラシの色を青色に変更しようとします。</span><span class="sxs-lookup"><span data-stu-id="6732f-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="6732f-110">前のコードは、何も実行しないように見えます。つまり、ブラシは、ブラシをアニメーション化した <xref:System.Windows.Media.Animation.ColorAnimation> によって指定された値である黄色のままです。</span><span class="sxs-lookup"><span data-stu-id="6732f-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="6732f-111">実際には、基になるプロパティ値 (基準値) は青色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6732f-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="6732f-112">しかし、有効な値または現在の値は黄色のままです。これは、<xref:System.Windows.Media.Animation.ColorAnimation> がまだ基準値をオーバーライドしているためです。</span><span class="sxs-lookup"><span data-stu-id="6732f-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="6732f-113">基準値が再度有効な値になるようにするには、アニメーションがプロパティに影響しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6732f-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="6732f-114">ストーリーボード アニメーションでこれを行うには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6732f-114">There are three ways to do this with storyboard animations:</span></span>  
  
- <span data-ttu-id="6732f-115">アニメーションの <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> プロパティを <xref:System.Windows.Media.Animation.FillBehavior.Stop> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6732f-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
- <span data-ttu-id="6732f-116">ストーリーボード全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="6732f-116">Remove the entire Storyboard.</span></span>  
  
- <span data-ttu-id="6732f-117">アニメーションを個々のプロパティから削除します。</span><span class="sxs-lookup"><span data-stu-id="6732f-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="6732f-118">アニメーションの FillBehavior プロパティを Stop に設定する</span><span class="sxs-lookup"><span data-stu-id="6732f-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="6732f-119"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> を <xref:System.Windows.Media.Animation.FillBehavior.Stop> に設定して、有効期間の終了に達した後はターゲット プロパティへの影響を停止するようにアニメーションに指示します。</span><span class="sxs-lookup"><span data-stu-id="6732f-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="6732f-120">ストーリーボード全体を削除する</span><span class="sxs-lookup"><span data-stu-id="6732f-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="6732f-121"><xref:System.Windows.Media.Animation.RemoveStoryboard> トリガーまたは <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> メソッドを使用して、ターゲット プロパティへの影響を停止するようにストーリーボード アニメーションに指示します。</span><span class="sxs-lookup"><span data-stu-id="6732f-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="6732f-122">この方法と <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> プロパティの設定との違いは、ストーリーボードをいつでも削除できることにあります。一方、<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> プロパティは、アニメーションが有効期間の終了に達したときにのみ効果があります。</span><span class="sxs-lookup"><span data-stu-id="6732f-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="6732f-123">アニメーションを個々のプロパティから削除する</span><span class="sxs-lookup"><span data-stu-id="6732f-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="6732f-124">アニメーションがプロパティに影響しないようにするもう 1 つの手法は、アニメーション化されるオブジェクトの <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> メソッドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="6732f-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="6732f-125">アニメーション化するプロパティを最初のパラメーターとして指定し、`null` を 2 番目のパラメーターとして指定します。</span><span class="sxs-lookup"><span data-stu-id="6732f-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="6732f-126">この手法は、非ストーリーボード アニメーションにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6732f-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6732f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6732f-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="6732f-128">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="6732f-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6732f-129">プロパティ アニメーションの手法の概要</span><span class="sxs-lookup"><span data-stu-id="6732f-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
