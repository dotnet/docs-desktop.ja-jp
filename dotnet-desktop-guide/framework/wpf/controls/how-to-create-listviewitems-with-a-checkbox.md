---
title: '方法: CheckBox を持つ ListViewItem を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985156"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="7e0e5-102">方法: CheckBox を持つ ListViewItem を作成する</span><span class="sxs-lookup"><span data-stu-id="7e0e5-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="7e0e5-103">この例では、<xref:System.Windows.Controls.GridView> を使用する <xref:System.Windows.Controls.ListView> コントロールに <xref:System.Windows.Controls.CheckBox> コントロールの列を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e0e5-104">例</span><span class="sxs-lookup"><span data-stu-id="7e0e5-104">Example</span></span>  
 <span data-ttu-id="7e0e5-105"><xref:System.Windows.Controls.ListView> に <xref:System.Windows.Controls.CheckBox> コントロールが含まれる列を作成するには、<xref:System.Windows.Controls.CheckBox> が含まれる <xref:System.Windows.DataTemplate> を作成します。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="7e0e5-106">次に、<xref:System.Windows.Controls.GridViewColumn> の <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> を <xref:System.Windows.DataTemplate> に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="7e0e5-107">次は、<xref:System.Windows.Controls.CheckBox> が含まれる <xref:System.Windows.DataTemplate> の例です。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="7e0e5-108">この例では、<xref:System.Windows.Controls.CheckBox> の <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> プロパティを、それが含まれる <xref:System.Windows.Controls.ListViewItem> の <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> プロパティ値にバインドしています。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="7e0e5-109">そのため、<xref:System.Windows.Controls.CheckBox> が含まれる <xref:System.Windows.Controls.ListViewItem> が選択されると、<xref:System.Windows.Controls.CheckBox> にチェックマークが入ります。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="7e0e5-110">次の例では、<xref:System.Windows.Controls.CheckBox> コントロールの列を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="7e0e5-111">列を作成するため、この例では、<xref:System.Windows.Controls.GridViewColumn> の <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> プロパティが <xref:System.Windows.DataTemplate> に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7e0e5-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="7e0e5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e0e5-112">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="7e0e5-113">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="7e0e5-113">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="7e0e5-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7e0e5-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="7e0e5-115">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="7e0e5-115">GridView Overview</span></span>](gridview-overview.md)
