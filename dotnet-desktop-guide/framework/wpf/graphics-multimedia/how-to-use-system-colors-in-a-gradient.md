---
title: '方法: グラデーションでシステム カラーを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983364"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="0fbe1-102">方法: グラデーションでシステム カラーを使用する</span><span class="sxs-lookup"><span data-stu-id="0fbe1-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="0fbe1-103">グラデーションでシステムカラーを使用するには、 *\<SystemColor>* クラスの color および *\<SystemColor>* colorkey 静的プロパティを使用して、 <xref:System.Windows.SystemColors> 色への参照を取得し *\<SystemColor>* ます。ここで、は目的のシステムカラーの名前です。</span><span class="sxs-lookup"><span data-stu-id="0fbe1-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="0fbe1-104">*\<SystemColor>* システムテーマの変更に応じて自動的に更新される動的参照を作成する場合は、colorkey プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fbe1-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="0fbe1-105">それ以外の場合は、色のプロパティを使用し *\<SystemColor>* ます。</span><span class="sxs-lookup"><span data-stu-id="0fbe1-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fbe1-106">例</span><span class="sxs-lookup"><span data-stu-id="0fbe1-106">Example</span></span>  
 <span data-ttu-id="0fbe1-107">次の例では、動的なシステム カラー リソースを使用して、グラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fbe1-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="0fbe1-108">次の例では、静的なシステム カラー リソースを使用して、グラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fbe1-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0fbe1-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fbe1-109">See also</span></span>

- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="0fbe1-110">システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="0fbe1-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="0fbe1-111">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="0fbe1-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
