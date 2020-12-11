---
title: '方法: バインディングの方向を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 6b3c6afde5e9fa1b778905b1a278bb295b6cbf11
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982620"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="21534-102">方法: バインディングの方向を指定する</span><span class="sxs-lookup"><span data-stu-id="21534-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="21534-103">この例では、バインドの更新先 (バインディング ターゲット (ターゲット) のプロパティのみ、バインディング ソース (ソース) のプロパティのみ、またはターゲットのプロパティとソースのプロパティの両方) を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21534-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21534-104">例</span><span class="sxs-lookup"><span data-stu-id="21534-104">Example</span></span>  
 <span data-ttu-id="21534-105">バインディングの方向を指定するには、<xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="21534-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="21534-106">バインディングの更新に使用できるオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="21534-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="21534-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>: ターゲットのプロパティまたはソースのプロパティのいずれかが変更されるたびに、ターゲットのプロパティまたはソースのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="21534-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="21534-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>: ソースのプロパティが変更された場合にのみ、ターゲットのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="21534-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="21534-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> では、アプリケーションが開始されたとき、または <xref:System.Windows.FrameworkElement.DataContext%2A> が変更されたときに、ターゲットのプロパティだけが更新されます。</span><span class="sxs-lookup"><span data-stu-id="21534-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="21534-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> では、ターゲットのプロパティが変更されると、ソースのプロパティが更新されます。</span><span class="sxs-lookup"><span data-stu-id="21534-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="21534-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> では、ターゲットのプロパティの既定の <xref:System.Windows.Data.Binding.Mode%2A> 値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="21534-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="21534-112">詳細については、<xref:System.Windows.Data.BindingMode> 列挙型のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="21534-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="21534-113"><xref:System.Windows.Data.Binding.Mode%2A> プロパティを設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="21534-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="21534-114">ソースの変更を検出するには (<xref:System.Windows.Data.BindingMode.OneWay> および <xref:System.Windows.Data.BindingMode.TwoWay> バインディングに適用)、ソースに <xref:System.ComponentModel.INotifyPropertyChanged> などの適切なプロパティ変更通知メカニズムを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21534-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="21534-115"><xref:System.ComponentModel.INotifyPropertyChanged> の実装の例については、「[プロパティの変更通知を実装する](how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21534-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="21534-116"><xref:System.Windows.Data.BindingMode.TwoWay> または <xref:System.Windows.Data.BindingMode.OneWayToSource> バインディングの場合は、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティを設定することによって、ソースの更新のタイミングを制御できます。</span><span class="sxs-lookup"><span data-stu-id="21534-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="21534-117">詳細については、「<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21534-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21534-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="21534-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="21534-119">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="21534-119">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="21534-120">方法トピック</span><span class="sxs-lookup"><span data-stu-id="21534-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
