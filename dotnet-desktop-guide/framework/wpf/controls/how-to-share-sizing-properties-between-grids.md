---
title: '方法: グリッド間でサイズ設定プロパティを共有する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985724"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="521b2-102">方法: グリッド間でサイズ設定プロパティを共有する</span><span class="sxs-lookup"><span data-stu-id="521b2-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="521b2-103">この例からは、サイズ設定の一貫性を維持する目的で <xref:System.Windows.Controls.Grid> 要素間の列と行のサイズ設定データを共有する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="521b2-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="521b2-104">例</span><span class="sxs-lookup"><span data-stu-id="521b2-104">Example</span></span>  
 <span data-ttu-id="521b2-105">次の例では、親 <xref:System.Windows.Controls.DockPanel> の子要素として 2 つの <xref:System.Windows.Controls.Grid> 要素が導入されます。</span><span class="sxs-lookup"><span data-stu-id="521b2-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="521b2-106"><xref:System.Windows.Controls.Grid> の <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 添付プロパティは親 <xref:System.Windows.Controls.DockPanel> で定義されます。</span><span class="sxs-lookup"><span data-stu-id="521b2-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="521b2-107">この例では、2 つの <xref:System.Windows.Controls.Button> 要素を使用してプロパティの値を操作します。各要素は、Boolean プロパティ値の 1 つを表します。</span><span class="sxs-lookup"><span data-stu-id="521b2-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="521b2-108"><xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> プロパティ値が `true` に設定されると、<xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> の各列または行メンバーでは、行または列のコンテンツに関係なく、サイズ設定情報が共有されます。</span><span class="sxs-lookup"><span data-stu-id="521b2-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="521b2-109">...</span><span class="sxs-lookup"><span data-stu-id="521b2-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="521b2-110">次のコードビハインド例では、ボタン <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントで発生するメソッドが処理されています。</span><span class="sxs-lookup"><span data-stu-id="521b2-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="521b2-111">この例では、これらのメソッドの <xref:System.Windows.Controls.TextBlock> 要素に対する呼び出しの結果を記述しています。この要素は、関連する獲得メソッドを使用して新しいプロパティの値を文字列として出力します。</span><span class="sxs-lookup"><span data-stu-id="521b2-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="521b2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="521b2-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="521b2-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="521b2-113">Panels Overview</span></span>](panels-overview.md)
