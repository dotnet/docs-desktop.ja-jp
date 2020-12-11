---
title: '方法: GridView を使用する ListView で行のスタイルを適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 586c549cca6ef3089b37427c7983bb39e56509bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974662"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="50043-102">方法: GridView を実装する ListView で行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="50043-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="50043-103">この例では、モードを使用するコントロールの行のスタイルを指定する方法を示し <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="50043-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50043-104">例</span><span class="sxs-lookup"><span data-stu-id="50043-104">Example</span></span>  
 <span data-ttu-id="50043-105"><xref:System.Windows.Controls.ListView> コントロールの行のスタイルを設定するには、<xref:System.Windows.Controls.ListView> コントロールで <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を設定します。</span><span class="sxs-lookup"><span data-stu-id="50043-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="50043-106"><xref:System.Windows.Controls.ListViewItem> オブジェクトとして表される項目のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="50043-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="50043-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を使用して、行の内容を表示するために使用される <xref:System.Windows.Controls.ControlTemplate> オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="50043-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="50043-108">以下の例の抜粋元である完全なサンプルでは、XML データベースに格納されている曲情報のコレクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="50043-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="50043-109">データベースの各曲にはレーティングフィールドがあり、このフィールドの値が曲情報の行を表示する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="50043-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="50043-110">次の例は、曲コレクション内の曲を表す <xref:System.Windows.Controls.ListViewItem> オブジェクトの <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="50043-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="50043-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を使用して、曲情報の行を表示する方法を指定する <xref:System.Windows.Controls.ControlTemplate> オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="50043-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="50043-112">次の例は、テキスト文字列 `"Strongly Recommended"` を行に追加する <xref:System.Windows.Controls.ControlTemplate> を示しています。</span><span class="sxs-lookup"><span data-stu-id="50043-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="50043-113">このテンプレートは <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 内で参照され、曲の評価の値が 5 の場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="50043-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="50043-114"><xref:System.Windows.Controls.ControlTemplate> には、<xref:System.Windows.Controls.GridView> ビュー モードで定義されている列に行の内容をレイアウトする <xref:System.Windows.Controls.GridViewRowPresenter> オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="50043-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="50043-115">次の例は、<xref:System.Windows.Controls.GridView> を定義しています。</span><span class="sxs-lookup"><span data-stu-id="50043-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="50043-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="50043-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="50043-117">方法トピック</span><span class="sxs-lookup"><span data-stu-id="50043-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="50043-118">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="50043-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="50043-119">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="50043-119">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
