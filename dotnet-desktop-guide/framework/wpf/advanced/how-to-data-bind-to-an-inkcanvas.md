---
title: '方法: InkCanvas にデータをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 5d3fc0ed7b6176d7bc68bf20af42c311b5563908
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984695"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="72a66-102">方法: InkCanvas にデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="72a66-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="72a66-103">例</span><span class="sxs-lookup"><span data-stu-id="72a66-103">Example</span></span>  
 <span data-ttu-id="72a66-104">次の例は、<xref:System.Windows.Controls.InkCanvas> の <xref:System.Windows.Controls.InkCanvas.Strokes%2A> プロパティを別の <xref:System.Windows.Controls.InkCanvas> にバインドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="72a66-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="72a66-105">次の例は、<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> プロパティをデータ ソースにバインドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="72a66-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="72a66-106">次の例では、XAML で 2 つの <xref:System.Windows.Controls.InkCanvas> オブジェクトを宣言し、それらと他のデータ ソースの間でデータ バインドを確立しています。</span><span class="sxs-lookup"><span data-stu-id="72a66-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="72a66-107">`ic` と呼ばれる最初の <xref:System.Windows.Controls.InkCanvas> は、2 つのデータ ソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="72a66-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="72a66-108">`ic` の <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> と <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> プロパティは、XAML で定義されている配列にバインドされる <xref:System.Windows.Controls.ListBox> オブジェクトにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="72a66-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="72a66-109">2 番目の <xref:System.Windows.Controls.InkCanvas> の <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>、<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>、<xref:System.Windows.Controls.InkCanvas.Strokes%2A> プロパティは、最初の <xref:System.Windows.Controls.InkCanvas>、`ic` にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="72a66-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
