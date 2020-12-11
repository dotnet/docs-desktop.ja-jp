---
title: '方法: ListView のカスタム表示モードを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985664"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="50c24-102">方法: ListView のカスタム表示モードを作成する</span><span class="sxs-lookup"><span data-stu-id="50c24-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="50c24-103">この例では、<xref:System.Windows.Controls.ListView> コントロールのカスタム <xref:System.Windows.Controls.ListView.View%2A> モードを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50c24-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50c24-104">例</span><span class="sxs-lookup"><span data-stu-id="50c24-104">Example</span></span>  
 <span data-ttu-id="50c24-105"><xref:System.Windows.Controls.ListView> コントロールのカスタム ビューを作成するときは、<xref:System.Windows.Controls.ViewBase> クラスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c24-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="50c24-106">次の例では、<xref:System.Windows.Controls.ViewBase> クラスから派生する `PlainView` という名前のビュー モードを示します。</span><span class="sxs-lookup"><span data-stu-id="50c24-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="50c24-107">カスタム ビューにスタイルを適用するには、<xref:System.Windows.Style> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="50c24-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="50c24-108">次の例では、`PlainView` ビュー モードに対する <xref:System.Windows.Style> を定義します。</span><span class="sxs-lookup"><span data-stu-id="50c24-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="50c24-109">前の例では、`PlainView` に対して定義されている <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> プロパティの値としてこのスタイルを設定しています。</span><span class="sxs-lookup"><span data-stu-id="50c24-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="50c24-110">カスタム ビュー モードでデータのレイアウトを定義するには、<xref:System.Windows.DataTemplate> オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="50c24-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="50c24-111">次の例では、`PlainView` ビュー モードでデータを表示するために使用できる <xref:System.Windows.DataTemplate> を定義します。</span><span class="sxs-lookup"><span data-stu-id="50c24-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="50c24-112">次の例では、前の例で定義されている <xref:System.Windows.DataTemplate> を使用する `PlainView` ビュー モードに対する <xref:System.Windows.ResourceKey> を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50c24-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="50c24-113"><xref:System.Windows.Controls.ListView.View%2A> プロパティにリソース キーを設定すると、<xref:System.Windows.Controls.ListView> コントロールでカスタム ビューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="50c24-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="50c24-114">次の例では、<xref:System.Windows.Controls.ListView> に対するビュー モードとして `PlainView` を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50c24-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="50c24-115">完全なサンプルについては、[複数のビューを使用する ListView (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) または[複数のビューを使用する ListView (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50c24-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c24-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="50c24-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="50c24-117">方法トピック</span><span class="sxs-lookup"><span data-stu-id="50c24-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="50c24-118">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="50c24-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="50c24-119">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="50c24-119">GridView Overview</span></span>](gridview-overview.md)
