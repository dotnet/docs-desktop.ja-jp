---
title: '方法: StackPanel にコンテンツを水平方向または垂直方向に配置する'
description: Windows Presentation Foundation の StackPanel でコンテンツの向き、および子コンテンツの HorizontalAlignment と VerticalAlignment を調整する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: b847ee4808c14622f24d758b9eb9ada28712ab3c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983336"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="8770e-103">方法: StackPanel にコンテンツを水平方向または垂直方向に配置する</span><span class="sxs-lookup"><span data-stu-id="8770e-103">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="8770e-104">この例では、<xref:System.Windows.Controls.StackPanel> 要素内のコンテンツの <xref:System.Windows.Controls.StackPanel.Orientation%2A> を調整する方法、および子コンテンツの <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> と <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> を調整する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8770e-104">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8770e-105">例</span><span class="sxs-lookup"><span data-stu-id="8770e-105">Example</span></span>  
 <span data-ttu-id="8770e-106">次の例では、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] で 3 つの <xref:System.Windows.Controls.ListBox> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="8770e-106">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="8770e-107">各 <xref:System.Windows.Controls.ListBox> は、<xref:System.Windows.Controls.StackPanel> の <xref:System.Windows.Controls.StackPanel.Orientation%2A>、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> プロパティの使用可能な値を表します。</span><span class="sxs-lookup"><span data-stu-id="8770e-107">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="8770e-108">ユーザーが <xref:System.Windows.Controls.ListBox> 要素のいずれかの値を選択すると、<xref:System.Windows.Controls.StackPanel> の関連付けられたプロパティとその子要素の <xref:System.Windows.Controls.Button> が変更されます。</span><span class="sxs-lookup"><span data-stu-id="8770e-108">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="8770e-109">次の分離コード ファイルによって、<xref:System.Windows.Controls.ListBox> 選択の変更に関連付けられているイベントへの変更が定義されます。</span><span class="sxs-lookup"><span data-stu-id="8770e-109">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="8770e-110"><xref:System.Windows.Controls.StackPanel> は <xref:System.Windows.FrameworkElement.Name%2A> `sp1` によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="8770e-110"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8770e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8770e-111">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="8770e-112">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8770e-112">Panels Overview</span></span>](panels-overview.md)
