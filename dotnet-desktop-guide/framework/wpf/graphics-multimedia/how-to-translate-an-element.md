---
title: '方法: 要素を変換する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983235"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="59992-102">方法: 要素を変換する</span><span class="sxs-lookup"><span data-stu-id="59992-102">How to: Translate an Element</span></span>
<span data-ttu-id="59992-103">この例では、<xref:System.Windows.Media.TranslateTransform> を使用して要素を平行移動 (移動) する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="59992-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="59992-104"><xref:System.Windows.Media.TranslateTransform> クラスは、絶対配置をサポートしていないパネル内の要素を移動する場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59992-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="59992-105">たとえば、<xref:System.Windows.Media.TranslateTransform> を要素の <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに適用することで、<xref:System.Windows.Controls.StackPanel> または <xref:System.Windows.Controls.DockPanel> 内の要素を移動できます。</span><span class="sxs-lookup"><span data-stu-id="59992-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="59992-106">要素を x 軸に沿って移動させる分量をピクセル単位で指定するには、<xref:System.Windows.Media.TranslateTransform> の <xref:System.Windows.Media.TranslateTransform.X%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="59992-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="59992-107">要素を y 軸に沿って移動させる分量をピクセル単位で指定するには、<xref:System.Windows.Media.TranslateTransform.Y%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="59992-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="59992-108">最後に、<xref:System.Windows.Media.TranslateTransform> を要素の <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに適用します。</span><span class="sxs-lookup"><span data-stu-id="59992-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="59992-109">次の例では、<xref:System.Windows.Media.TranslateTransform> を使用して、要素を右方向に 50 ピクセル、下方向に 50 ピクセル移動します。</span><span class="sxs-lookup"><span data-stu-id="59992-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59992-110">例</span><span class="sxs-lookup"><span data-stu-id="59992-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="59992-111">サンプル全体については、「[2D 変換のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="59992-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59992-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="59992-112">See also</span></span>

- [<span data-ttu-id="59992-113">変換の概要</span><span class="sxs-lookup"><span data-stu-id="59992-113">Transforms Overview</span></span>](transforms-overview.md)
