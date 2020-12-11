---
title: '方法: システム ブラシで領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 26511c577bf06b016dfc69cedc7fce2bafb35f32
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983260"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="c8ce9-102">方法: システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="c8ce9-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="c8ce9-103"><xref:System.Windows.SystemColors> クラスを使用すると、<xref:System.Windows.SystemColors.ControlBrush%2A>、<xref:System.Windows.SystemColors.ControlBrushKey%2A>、<xref:System.Windows.SystemColors.DesktopBrush%2A> などのシステム ブラシと色を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="c8ce9-104">システム ブラシは、指定したシステム カラーで領域を塗りつぶす <xref:System.Windows.Media.SolidColorBrush> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="c8ce9-105">システム ブラシは、常に純色の塗りつぶしを生成します。グラデーションを作成するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="c8ce9-106">システム ブラシは、静的なリソースとしても、動的なリソースとしても使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="c8ce9-107">アプリケーションの実行中にユーザーがシステム ブラシを変更したときにブラシを自動的に更新する場合は、動的なリソースを使用します。それ以外の場合は、静的なリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="c8ce9-108">SystemColors クラスには、厳密な名前付け規則に従うさまざまな静的プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
- <span data-ttu-id="c8ce9-109">*\<SystemColor>* 塗り</span><span class="sxs-lookup"><span data-stu-id="c8ce9-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="c8ce9-110">指定したシステム カラーの <xref:System.Windows.Media.SolidColorBrush> への静的な参照が取得されます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
- <span data-ttu-id="c8ce9-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="c8ce9-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="c8ce9-112">指定したシステム カラーの <xref:System.Windows.Media.SolidColorBrush> への動的な参照が取得されます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
- <span data-ttu-id="c8ce9-113">*\<SystemColor>* 色</span><span class="sxs-lookup"><span data-stu-id="c8ce9-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="c8ce9-114">指定したシステム カラーの <xref:System.Windows.Media.Color> 構造体への静的な参照が取得されます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
- <span data-ttu-id="c8ce9-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="c8ce9-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="c8ce9-116">指定したシステム カラーの <xref:System.Windows.Media.Color> 構造体への動的な参照が取得されます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="c8ce9-117">システム カラーは <xref:System.Windows.Media.Color> 構造体であり、ブラシの構成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="c8ce9-118">たとえば、<xref:System.Windows.Media.LinearGradientBrush> オブジェクトのグラデーションの終了位置の <xref:System.Windows.Media.GradientStop.Color%2A> プロパティにシステム カラーを設定することで、システム カラーを使用してグラデーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="c8ce9-119">例については、「[グラデーションでシステム カラーを使用する](how-to-use-system-colors-in-a-gradient.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-119">For an example, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8ce9-120">例</span><span class="sxs-lookup"><span data-stu-id="c8ce9-120">Example</span></span>  
 <span data-ttu-id="c8ce9-121">次の例では、動的なシステム ブラシの参照を使用して、ボタンの背景を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="c8ce9-122">次の例では、静的なシステム ブラシの参照を使用して、ボタンの背景を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="c8ce9-123">グラデーションでのシステム カラーの使用方法を示す例については、「[グラデーションでシステム カラーを使用する](how-to-use-system-colors-in-a-gradient.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8ce9-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ce9-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8ce9-124">See also</span></span>

- [<span data-ttu-id="c8ce9-125">グラデーションでシステム カラーを使用する</span><span class="sxs-lookup"><span data-stu-id="c8ce9-125">Use System Colors in a Gradient</span></span>](how-to-use-system-colors-in-a-gradient.md)
- [<span data-ttu-id="c8ce9-126">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="c8ce9-126">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
