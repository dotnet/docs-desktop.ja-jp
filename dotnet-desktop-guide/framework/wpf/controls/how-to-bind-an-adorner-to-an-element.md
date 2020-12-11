---
title: '方法: 要素に装飾をバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 951643602b09a522d23a6449aefa4be41e051a40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983499"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="181ca-102">方法: 要素に装飾をバインドする</span><span class="sxs-lookup"><span data-stu-id="181ca-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="181ca-103">この例では、指定した <xref:System.Windows.UIElement> にプログラムで装飾をバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="181ca-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="181ca-104">例</span><span class="sxs-lookup"><span data-stu-id="181ca-104">Example</span></span>  
 <span data-ttu-id="181ca-105">特定の <xref:System.Windows.UIElement> に装飾をバインドするには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="181ca-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1. <span data-ttu-id="181ca-106">`static` メソッド <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> を呼び出して、装飾対象となる <xref:System.Windows.UIElement> の <xref:System.Windows.Documents.AdornerLayer> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="181ca-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="181ca-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> は、指定した **UIElement** を起点としてビジュアル ツリーを上に探索し、最初に見つかった装飾層を返します。</span><span class="sxs-lookup"><span data-stu-id="181ca-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="181ca-108">(装飾層が見つからない場合、メソッドにより null が返されます)。</span><span class="sxs-lookup"><span data-stu-id="181ca-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2. <span data-ttu-id="181ca-109"><xref:System.Windows.Documents.AdornerLayer.Add%2A> メソッドを呼び出して、対象の **UIElement** に装飾をバインドします。</span><span class="sxs-lookup"><span data-stu-id="181ca-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="181ca-110">次の例では、SimpleCircleAdorner (上図参照) を *myTextBox* という名前の <xref:System.Windows.Controls.TextBox> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="181ca-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> <span data-ttu-id="181ca-111">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を使用して、装飾を別の要素にバインドする方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="181ca-111">Using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181ca-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="181ca-112">See also</span></span>

- [<span data-ttu-id="181ca-113">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="181ca-113">Adorners Overview</span></span>](adorners-overview.md)
