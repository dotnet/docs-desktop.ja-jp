---
title: '方法: 列挙値にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: c92f1f00aa3feb37b70aa9a3647265236a1625b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974486"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="b1d92-102">方法: 列挙値にバインドする</span><span class="sxs-lookup"><span data-stu-id="b1d92-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="b1d92-103">この例では、列挙型の GetValues メソッドにバインドすることによって列挙型にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1d92-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1d92-104">例</span><span class="sxs-lookup"><span data-stu-id="b1d92-104">Example</span></span>  
 <span data-ttu-id="b1d92-105">次の例の <xref:System.Windows.Controls.ListBox> では、データ バインディングを通じて <xref:System.Windows.HorizontalAlignment> 列挙値の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1d92-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="b1d92-106"><xref:System.Windows.Controls.ListBox> と <xref:System.Windows.Controls.Button> は、<xref:System.Windows.Controls.ListBox> 内の値を選択することにより <xref:System.Windows.Controls.Button> の <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティ値を変更できるようにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="b1d92-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="b1d92-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1d92-107">See also</span></span>

- [<span data-ttu-id="b1d92-108">メソッドにバインドする</span><span class="sxs-lookup"><span data-stu-id="b1d92-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="b1d92-109">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="b1d92-109">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b1d92-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b1d92-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
