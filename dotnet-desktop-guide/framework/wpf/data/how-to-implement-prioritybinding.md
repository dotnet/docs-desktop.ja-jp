---
title: '方法: PriorityBinding を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 694679183f92c9737bbdb511b4ebd5a4bf2185f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985791"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="b3a08-102">方法: PriorityBinding を実装する</span><span class="sxs-lookup"><span data-stu-id="b3a08-102">How to: Implement PriorityBinding</span></span>

<span data-ttu-id="b3a08-103">[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の <xref:System.Windows.Data.PriorityBinding> は、バインディングのリストを指定することによって機能します。</span><span class="sxs-lookup"><span data-stu-id="b3a08-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="b3a08-104">バインディングのリストは、優先順位が最も高いものから低いものの順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="b3a08-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="b3a08-105">処理時に最も優先順位の高いバインディングから値が正常に返された場合、リスト内の他のバインディングを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b3a08-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="b3a08-106">最も優先順位の高いバインディングの評価に長い時間がかかっているため、優先順位が高いバインディングから値が正常に返されるまで、次に優先順位が高くて値が正常に返されるバインディングが使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3a08-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3a08-107">例</span><span class="sxs-lookup"><span data-stu-id="b3a08-107">Example</span></span>  

 <span data-ttu-id="b3a08-108"><xref:System.Windows.Data.PriorityBinding> 動作を示すため、3 つのプロパティ `FastDP`、`SlowerDP`、`SlowestDP` を含む `AsyncDataSource` オブジェクトが作成されています。</span><span class="sxs-lookup"><span data-stu-id="b3a08-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="b3a08-109">`FastDP` の get アクセサーでは、`_fastDP` データ メンバーの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="b3a08-110">`SlowerDP` の get アクセサーでは、3 秒間待ってから、`_slowerDP` データ メンバーの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="b3a08-111">`SlowestDP` の get アクセサーでは、5 秒間待ってから、`_slowestDP` データ メンバーの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3a08-112">この例は、デモンストレーション目的のみで提供されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="b3a08-113">.NET のガイドラインでは、フィールド セットよりはるかに遅いプロパティは定義しないように推奨されています。</span><span class="sxs-lookup"><span data-stu-id="b3a08-113">The .NET guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="b3a08-114">詳細については、「[プロパティとメソッドの選択](/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a08-114">For more information, see [Choosing Between Properties and Methods](/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="b3a08-115"><xref:System.Windows.Controls.TextBlock.Text%2A> プロパティは、<xref:System.Windows.Data.PriorityBinding> を使用して上記の `AsyncDS` にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="b3a08-116">バインディング エンジンでは、<xref:System.Windows.Data.Binding> オブジェクトを処理するときに、`SlowestDP` プロパティにバインドされている最初の <xref:System.Windows.Data.Binding> から開始されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="b3a08-117">この <xref:System.Windows.Data.Binding> は処理されても 5 秒間スリープ状態になるため値が正常に返されないので、次の <xref:System.Windows.Data.Binding> 要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="b3a08-118">次の <xref:System.Windows.Data.Binding> も 3 秒間スリープするため、値が正常に返されません。</span><span class="sxs-lookup"><span data-stu-id="b3a08-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="b3a08-119">バインディング エンジンは、次に、`FastDP` プロパティにバインドされている <xref:System.Windows.Data.Binding> 要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="b3a08-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="b3a08-120">この <xref:System.Windows.Data.Binding> では、値 "Fast Value" が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="b3a08-121"><xref:System.Windows.Controls.TextBlock> に値 "Fast Value" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="b3a08-122">3 秒経過すると、`SlowerDP` プロパティから値 "Slower Value" が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="b3a08-123"><xref:System.Windows.Controls.TextBlock> に、値 "Slower Value" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="b3a08-124">5 秒経過すると、`SlowestDP` プロパティから値 "Slowest Value" が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="b3a08-125">そのバインディングは、リストの先頭にあるので最も高い優先順位です。</span><span class="sxs-lookup"><span data-stu-id="b3a08-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="b3a08-126"><xref:System.Windows.Controls.TextBlock> に値 "Slowest Value" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3a08-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="b3a08-127">何をもってバインディングからの戻り値が成功と見なされるかについては、<xref:System.Windows.Data.PriorityBinding> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a08-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a08-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3a08-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b3a08-129">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="b3a08-129">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b3a08-130">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b3a08-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
