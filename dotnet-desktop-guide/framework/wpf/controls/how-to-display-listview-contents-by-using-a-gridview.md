---
title: '方法: GridView を使用して ListView コンテンツを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985124"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="88f66-102">方法: GridView を使用して ListView コンテンツを表示する</span><span class="sxs-lookup"><span data-stu-id="88f66-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="88f66-103">この例からは、<xref:System.Windows.Controls.ListView> コントロールの <xref:System.Windows.Controls.GridView> 表示モードを定義する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="88f66-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88f66-104">例</span><span class="sxs-lookup"><span data-stu-id="88f66-104">Example</span></span>  
 <span data-ttu-id="88f66-105"><xref:System.Windows.Controls.GridViewColumn> オブジェクトを指定することによって <xref:System.Windows.Controls.GridView> の表示モードを定義できます。</span><span class="sxs-lookup"><span data-stu-id="88f66-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="88f66-106">次の例では、<xref:System.Windows.Controls.ListView> コントロールに指定されているデータ コンテンツにバインドされる <xref:System.Windows.Controls.GridViewColumn> オブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="88f66-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="88f66-107">この <xref:System.Windows.Controls.GridView> の例では、<xref:System.Windows.Controls.ListView> コントロールの <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> として設定される `EmployeeInfoDataSource` の `FirstName`、`LastName`、`EmployeeNumber` フィールドにマッピングされる 3 つの <xref:System.Windows.Controls.GridViewColumn> オブジェクトが指定されます。</span><span class="sxs-lookup"><span data-stu-id="88f66-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="88f66-108">この例がどのように表示されるかを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="88f66-108">The following illustration shows how this example appears.</span></span>  
  
 ![GridView の出力が表示された ListView のスクリーンショット。](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a><span data-ttu-id="88f66-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="88f66-110">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="88f66-111">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="88f66-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="88f66-112">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="88f66-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="88f66-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="88f66-113">How-to Topics</span></span>](listview-how-to-topics.md)
