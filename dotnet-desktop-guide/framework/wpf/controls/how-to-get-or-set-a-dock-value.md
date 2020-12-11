---
title: '方法: Dock の値を取得または設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982771"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="7ed64-102">方法: Dock の値を取得または設定する</span><span class="sxs-lookup"><span data-stu-id="7ed64-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="7ed64-103">次の例では、オブジェクトの <xref:System.Windows.Controls.Dock> 値を割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7ed64-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="7ed64-104">例では、<xref:System.Windows.Controls.DockPanel> の <xref:System.Windows.Controls.DockPanel.GetDock%2A> メソッドと <xref:System.Windows.Controls.DockPanel.SetDock%2A> メソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ed64-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ed64-105">例</span><span class="sxs-lookup"><span data-stu-id="7ed64-105">Example</span></span>  
 <span data-ttu-id="7ed64-106">例では、<xref:System.Windows.Controls.TextBlock> 要素のインスタンス `txt1` が作成され、<xref:System.Windows.Controls.DockPanel> の <xref:System.Windows.Controls.DockPanel.SetDock%2A> メソッドを利用して `Top` の <xref:System.Windows.Controls.Dock> 値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7ed64-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="7ed64-107">次に、<xref:System.Windows.Controls.DockPanel.GetDock%2A> メソッドを利用し、<xref:System.Windows.Controls.Dock> プロパティの値が <xref:System.Windows.Controls.TextBlock> 要素の <xref:System.Windows.Controls.TextBlock.Text%2A> に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7ed64-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="7ed64-108">この例では最後に、<xref:System.Windows.Controls.TextBlock> 要素が親 <xref:System.Windows.Controls.DockPanel> の `dp1` に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7ed64-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7ed64-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ed64-109">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [<span data-ttu-id="7ed64-110">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="7ed64-110">Panels Overview</span></span>](panels-overview.md)
