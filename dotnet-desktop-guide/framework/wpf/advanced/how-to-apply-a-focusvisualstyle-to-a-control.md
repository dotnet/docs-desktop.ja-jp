---
title: '方法: FocusVisualStyle をコントロールに適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: c27994bfbc77f7cbe360ad3aab94827900e52232
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982299"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="0e0e9-102">方法: FocusVisualStyle をコントロールに適用する</span><span class="sxs-lookup"><span data-stu-id="0e0e9-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="0e0e9-103">この例では、<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> プロパティを使用して、リソースにフォーカス表示スタイルを作成し、そのスタイルをコントロールに適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e0e9-104">例</span><span class="sxs-lookup"><span data-stu-id="0e0e9-104">Example</span></span>  
 <span data-ttu-id="0e0e9-105">次の例では、コントロールがユーザー インターフェイス (UI)[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] でキーボード フォーカスされている場合にのみ適用される追加のコントロール複合を作成するスタイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="0e0e9-106">これは、<xref:System.Windows.Controls.ControlTemplate> でスタイルを定義して、<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> プロパティを設定するときに、そのスタイルをリソースとして参照することで実現します。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="0e0e9-107">枠線のような外部の四角形は、四角形の領域の外側に配置されます。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="0e0e9-108">特に変更がない限り、スタイルのサイズ変更では、フォーカス表示スタイルが適用される四角形コントロールの <xref:System.Windows.FrameworkElement.ActualHeight%2A> と <xref:System.Windows.FrameworkElement.ActualWidth%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="0e0e9-109">この例では、<xref:System.Windows.FrameworkElement.Margin%2A> に負の値を設定して、フォーカスされたコントロールの外に枠線が少し表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="0e0e9-110"><xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> は、明示的なスタイルまたはテーマ スタイルから取得したコントロール テンプレート スタイルへの追加です。コントロールのプライマリ スタイルは、<xref:System.Windows.Controls.ControlTemplate> を使用し、そのスタイルを <xref:System.Windows.FrameworkElement.Style%2A> プロパティに設定することで作成できます。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="0e0e9-111">フォーカス表示スタイルは、フォーカスできる要素ごとに異なるものを使用するのではなく、テーマまたは UI 全体で一貫したものを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="0e0e9-112">詳細については、「[コントロールのフォーカスのスタイルと FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e0e9-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0e9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e0e9-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="0e0e9-114">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0e0e9-114">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="0e0e9-115">コントロールのフォーカスのスタイルと FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="0e0e9-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
