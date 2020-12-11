---
title: '方法: トリガーを使用して、ListView で選択された項目のスタイルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983687"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="cfbdc-102">方法: トリガーを使用して、ListView で選択された項目のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="cfbdc-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="cfbdc-103">この例は、<xref:System.Windows.Controls.ListViewItem> コントロールの <xref:System.Windows.Style.Triggers%2A> を定義して、<xref:System.Windows.Controls.ListViewItem> のプロパティ値の変更に応じて <xref:System.Windows.Controls.ListViewItem> の <xref:System.Windows.Style> が変更されるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfbdc-104">例</span><span class="sxs-lookup"><span data-stu-id="cfbdc-104">Example</span></span>  
 <span data-ttu-id="cfbdc-105">プロパティの変更に応じて <xref:System.Windows.Controls.ListViewItem> の <xref:System.Windows.Style> を変更する場合は、<xref:System.Windows.Style> の変更に対して <xref:System.Windows.Style.Triggers%2A> を定義します。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="cfbdc-106">次の例では、<xref:System.Windows.Controls.Control.Foreground%2A> プロパティを <xref:System.Windows.Media.Brushes.Blue%2A> に設定し、<xref:System.Windows.UIElement.IsMouseOver%2A> プロパティが `true` に変更されたときに <xref:System.Windows.Input.CursorType.Hand> を表示するように <xref:System.Windows.FrameworkElement.Cursor%2A> を変更する <xref:System.Windows.Trigger> を定義しています。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="cfbdc-107">次の例では、<xref:System.Windows.Controls.ListViewItem> が選択された項目で、キーボード フォーカスがある場合に、<xref:System.Windows.Controls.ListViewItem> の <xref:System.Windows.Controls.Control.Foreground%2A> プロパティを <xref:System.Windows.Media.Brushes.Yellow%2A> に設定する <xref:System.Windows.MultiTrigger> を定義しています。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="cfbdc-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfbdc-108">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="cfbdc-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="cfbdc-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="cfbdc-110">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="cfbdc-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="cfbdc-111">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="cfbdc-111">GridView Overview</span></span>](gridview-overview.md)
