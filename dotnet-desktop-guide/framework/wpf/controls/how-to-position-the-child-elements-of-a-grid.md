---
title: '方法: グリッドの子要素を配置する'
description: Windows Presentation Foundation の Grid で定義されている get と set メソッドを使用して、子要素を配置する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985820"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="1fb71-103">方法: グリッドの子要素を配置する</span><span class="sxs-lookup"><span data-stu-id="1fb71-103">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="1fb71-104">この例では、<xref:System.Windows.Controls.Grid> で定義されている get メソッドと set メソッドを使用して、子要素を配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1fb71-104">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fb71-105">例</span><span class="sxs-lookup"><span data-stu-id="1fb71-105">Example</span></span>  
 <span data-ttu-id="1fb71-106">次の例では、3 つの列と 3 つの行を持つ親 <xref:System.Windows.Controls.Grid> 要素 (`grid1`) を定義します。</span><span class="sxs-lookup"><span data-stu-id="1fb71-106">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="1fb71-107">子 <xref:System.Windows.Shapes.Rectangle> 要素 (`rect1`) は、列位置 0、行位置 0 の <xref:System.Windows.Controls.Grid> に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1fb71-107">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="1fb71-108"><xref:System.Windows.Controls.Button> 要素によって表されるメソッドを呼び出すことで、<xref:System.Windows.Controls.Grid> 内の <xref:System.Windows.Shapes.Rectangle> 要素の位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1fb71-108"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="1fb71-109">ユーザーがボタンをクリックすると、関連するメソッドがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="1fb71-109">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="1fb71-110">次のコードビハインドの例では、ボタンの <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントが発生するメソッドが処理されています。</span><span class="sxs-lookup"><span data-stu-id="1fb71-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="1fb71-111">この例では、これらのメソッドの呼び出しが <xref:System.Windows.Controls.TextBlock> 要素に書き込まれ、そこで関連する get メソッドを使用して新しいプロパティ値が文字列として出力されます。</span><span class="sxs-lookup"><span data-stu-id="1fb71-111">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="1fb71-112">完成した結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fb71-112">Here is the finished result!</span></span>

 ![2 つの列を持つ WPF ユーザー インターフェイスを示すスクリーンショット。右側には 3 × 3 のグリッドがあり、左側にはグリッドの列と行の間で色付きの四角形を移動するボタンがある](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="1fb71-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fb71-114">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="1fb71-115">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="1fb71-115">Panels Overview</span></span>](panels-overview.md)
