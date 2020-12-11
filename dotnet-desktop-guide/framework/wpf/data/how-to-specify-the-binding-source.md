---
title: '方法: バインディング ソースを指定する'
description: この例では、Windows Presentation Foundation (WPF) でバインディング ソースを指定する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
ms.openlocfilehash: d78a49cae9c28ae385df2ac89356b1b57e7c167c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984451"
---
# <a name="how-to-specify-the-binding-source"></a><span data-ttu-id="5c9b4-103">方法: バインディング ソースを指定する</span><span class="sxs-lookup"><span data-stu-id="5c9b4-103">How to: Specify the Binding Source</span></span>
<span data-ttu-id="5c9b4-104">データ バインディングでは、バインド ソース オブジェクトとは、そこからデータを取得するオブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-104">In data binding, the binding source object refers to the object you obtain your data from.</span></span> <span data-ttu-id="5c9b4-105">このトピックでは、バインド ソースを指定するさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-105">This topic describes the different ways of specifying the binding source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c9b4-106">例</span><span class="sxs-lookup"><span data-stu-id="5c9b4-106">Example</span></span>  
 <span data-ttu-id="5c9b4-107">複数のプロパティを共通ソースにバインドする場合は、`DataContext` を使用できます。これは、すべてのデータ バインド プロパティが共通ソースを継承するスコープを確立するための便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-107">If you are binding several properties to a common source, you want to use the `DataContext` property, which provides a convenient way to establish a scope within which all data-bound properties inherit a common source.</span></span>  
  
 <span data-ttu-id="5c9b4-108">次の例では、アプリケーションのルート要素にデータ コンテキストが確立されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-108">In the following example, the data context is established on the root element of the application.</span></span> <span data-ttu-id="5c9b4-109">これにより、すべての子要素がそのデータ コンテキストを継承することができます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-109">This allows all child elements to inherit that data context.</span></span> <span data-ttu-id="5c9b4-110">バインドするデータは、マッピングを通して直接参照され、リソース キー `incomeDataSource` が与えられるカスタム データ クラス `NetIncome` から取得されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-110">Data for the binding comes from a custom data class, `NetIncome`, referenced directly through a mapping and given the resource key of `incomeDataSource`.</span></span>  
  
 [!code-xaml[DirectionalBinding#DataContext1](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xaml[DirectionalBinding#DataContext2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 <span data-ttu-id="5c9b4-111">次の例は、`NetIncome` クラスの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-111">The following example shows the definition of the `NetIncome` class.</span></span>  
  
 [!code-csharp[DirectionalBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
> <span data-ttu-id="5c9b4-112">上記の例では、マークアップ内のオブジェクトをインスタンス化し、それをリソースとして使用しています。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-112">The above example instantiates the object in markup and uses it as a resource.</span></span> <span data-ttu-id="5c9b4-113">コードで既にインスタンス化されているオブジェクトにバインドする場合は、`DataContext` プロパティをプログラムで設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-113">If you want to bind to an object that has already been instantiated in code, you need to set the `DataContext` property programmatically.</span></span> <span data-ttu-id="5c9b4-114">例については、「[方法: XAML でデータをバインディング可能にする](how-to-make-data-available-for-binding-in-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-114">For an example, see [Make Data Available for Binding in XAML](how-to-make-data-available-for-binding-in-xaml.md).</span></span>  
  
 <span data-ttu-id="5c9b4-115">個々のバインドでソースを明示的に指定する場合は、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-115">Alternatively, if you want to specify the source on your individual bindings explicitly, you have the following options.</span></span> <span data-ttu-id="5c9b4-116">これらは、継承されたデータ コンテキストに優先します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-116">These take precedence over the inherited data context.</span></span>  
  
|<span data-ttu-id="5c9b4-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5c9b4-117">Property</span></span>|<span data-ttu-id="5c9b4-118">説明</span><span class="sxs-lookup"><span data-stu-id="5c9b4-118">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|<span data-ttu-id="5c9b4-119">オブジェクトのインスタンスにソースを設定するには、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-119">You use this property to set the source to an instance of an object.</span></span> <span data-ttu-id="5c9b4-120">複数のプロパティが同じデータ コンテキストを継承するスコープを確立する機能が不要な場合は、`DataContext` プロパティの代わりに <xref:System.Windows.Data.Binding.Source%2A> プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-120">If you do not need the functionality of establishing a scope in which several properties inherit the same data context, you can use the <xref:System.Windows.Data.Binding.Source%2A> property instead of the `DataContext` property.</span></span> <span data-ttu-id="5c9b4-121">詳細については、「<xref:System.Windows.Data.Binding.Source%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-121">For more information, see <xref:System.Windows.Data.Binding.Source%2A>.</span></span>|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|<span data-ttu-id="5c9b4-122">これは、バインディング ターゲットの場所を基準としてソースを指定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-122">This is useful when you want to specify the source relative to where your binding target is.</span></span> <span data-ttu-id="5c9b4-123">このプロパティを使用できる一般的なシナリオとして、要素の 1 つのプロパティを同じ要素の別のプロパティにバインドする場合や、スタイルまたはテンプレート内のバインドを定義する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-123">Some common scenarios where you may use this property is when you want to bind one property of your element to another property of the same element or if you are defining a binding in a style or a template.</span></span> <span data-ttu-id="5c9b4-124">詳細については、「<xref:System.Windows.Data.Binding.RelativeSource%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-124">For more information, see <xref:System.Windows.Data.Binding.RelativeSource%2A>.</span></span>|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|<span data-ttu-id="5c9b4-125">バインド先の要素を表す文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-125">You specify a string that represents the element you want to bind to.</span></span> <span data-ttu-id="5c9b4-126">これは、アプリケーションの別の要素のプロパティにバインドする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-126">This is useful when you want to bind to the property of another element on your application.</span></span> <span data-ttu-id="5c9b4-127">たとえば、<xref:System.Windows.Controls.Slider> を使用してアプリケーション内の別のコントロールの高さを制御する場合、またはコントロールの <xref:System.Windows.Controls.ContentControl.Content%2A> を <xref:System.Windows.Controls.ListBox> コントロールの <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> プロパティにバインドする場合などです。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-127">For example, if you want to use a <xref:System.Windows.Controls.Slider> to control the height of another control in your application, or if you want to bind the <xref:System.Windows.Controls.ContentControl.Content%2A> of your control to the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property of your <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="5c9b4-128">詳細については、「<xref:System.Windows.Data.Binding.ElementName%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-128">For more information, see <xref:System.Windows.Data.Binding.ElementName%2A>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c9b4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c9b4-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5c9b4-130">プロパティ値の継承</span><span class="sxs-lookup"><span data-stu-id="5c9b4-130">Property Value Inheritance</span></span>](../advanced/property-value-inheritance.md)
- [<span data-ttu-id="5c9b4-131">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="5c9b4-131">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="5c9b4-132">バインディング宣言の概要</span><span class="sxs-lookup"><span data-stu-id="5c9b4-132">Binding Declarations Overview</span></span>](binding-declarations-overview.md)
- [<span data-ttu-id="5c9b4-133">方法トピック</span><span class="sxs-lookup"><span data-stu-id="5c9b4-133">How-to Topics</span></span>](data-binding-how-to-topics.md)
