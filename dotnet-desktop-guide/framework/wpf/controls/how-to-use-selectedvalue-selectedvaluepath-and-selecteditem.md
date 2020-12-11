---
title: '方法: SelectedValue、SelectedValuePath、および SelectedItem を使用する'
description: SelectedValue および SelectedValuePath プロパティを使用して、Windows Presentation Foundation TreeView の SelectedItem に値を指定する方法について学習します。
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982876"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="f663a-103">方法: SelectedValue、SelectedValuePath、および SelectedItem を使用する</span><span class="sxs-lookup"><span data-stu-id="f663a-103">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="f663a-104">この例からは、<xref:System.Windows.Controls.TreeView.SelectedValue%2A> プロパティと <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> プロパティを使用し、<xref:System.Windows.Controls.TreeView> の <xref:System.Windows.Controls.TreeView.SelectedItem%2A> に値を指定する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="f663a-104">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f663a-105">例</span><span class="sxs-lookup"><span data-stu-id="f663a-105">Example</span></span>  
 <span data-ttu-id="f663a-106"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> プロパティからは、<xref:System.Windows.Controls.TreeView> 内の <xref:System.Windows.Controls.TreeView.SelectedValue%2A> に <xref:System.Windows.Controls.TreeView.SelectedItem%2A> を指定する方法が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f663a-106">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="f663a-107"><xref:System.Windows.Controls.TreeView.SelectedItem%2A> は <xref:System.Windows.Controls.ItemsControl.Items%2A> コレクション内のオブジェクトです。<xref:System.Windows.Controls.TreeView> には、選択した項目の単一プロパティの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f663a-107">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="f663a-108"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> プロパティによって、<xref:System.Windows.Controls.TreeView.SelectedValue%2A> プロパティの値を決定する目的で使用されるプロパティのパスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f663a-108">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="f663a-109">このトピックの例はこの概念を説明するものです。</span><span class="sxs-lookup"><span data-stu-id="f663a-109">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="f663a-110">次の例では、社員情報が含まれる <xref:System.Windows.Data.XmlDataProvider> を示します。</span><span class="sxs-lookup"><span data-stu-id="f663a-110">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="f663a-111">次の例では、`Employee` の `EmployeeName` と `EmployeeWorkDay` を表示する <xref:System.Windows.HierarchicalDataTemplate> が定義されます。</span><span class="sxs-lookup"><span data-stu-id="f663a-111">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="f663a-112"><xref:System.Windows.HierarchicalDataTemplate> ではテンプレートの一部として `EmployeeNumber` が指定されないことにご留意ください。</span><span class="sxs-lookup"><span data-stu-id="f663a-112">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="f663a-113">次の例では、前に定義した <xref:System.Windows.HierarchicalDataTemplate> を使用し、<xref:System.Windows.Controls.TreeView.SelectedValue%2A> プロパティを `EmployeeNumber` に設定する <xref:System.Windows.Controls.TreeView> を示します。</span><span class="sxs-lookup"><span data-stu-id="f663a-113">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="f663a-114"><xref:System.Windows.Controls.TreeView> で `EmployeeName` を選択すると、<xref:System.Windows.Controls.TreeView.SelectedItem%2A> プロパティから、選択した `EmployeeName` に対応する `EmployeeInfo` データ項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="f663a-114">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="f663a-115">ただし、この <xref:System.Windows.Controls.TreeView> の <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> が `EmployeeNumber` に設定されているため、<xref:System.Windows.Controls.TreeView.SelectedValue%2A> は `EmployeeNumber` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f663a-115">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="f663a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f663a-116">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="f663a-117">TreeView の概要</span><span class="sxs-lookup"><span data-stu-id="f663a-117">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="f663a-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f663a-118">How-to Topics</span></span>](treeview-how-to-topics.md)
