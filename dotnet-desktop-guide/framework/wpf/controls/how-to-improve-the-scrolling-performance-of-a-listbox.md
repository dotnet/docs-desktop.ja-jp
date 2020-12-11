---
title: '方法: ListBox のスクロール速度を向上させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983896"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="c88b1-102">方法: ListBox のスクロール速度を向上させる</span><span class="sxs-lookup"><span data-stu-id="c88b1-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="c88b1-103"><xref:System.Windows.Controls.ListBox> に含まれる項目が多い場合、ユーザーがマウス ホイールを使用したり、スクロール バーのつまみをドラッグしたりして <xref:System.Windows.Controls.ListBox> をスクロールするときに、ユーザー インターフェイスの応答が遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="c88b1-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="c88b1-104">`VirtualizingStackPanel.VirtualizationMode` 添付プロパティを <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> に設定することで、ユーザーがスクロールしたときの <xref:System.Windows.Controls.ListBox> のパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="c88b1-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c88b1-105">例</span><span class="sxs-lookup"><span data-stu-id="c88b1-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="c88b1-106">説明</span><span class="sxs-lookup"><span data-stu-id="c88b1-106">Description</span></span>  
<span data-ttu-id="c88b1-107">次の例では、<xref:System.Windows.Controls.ListBox> を作成し、`VirtualizingStackPanel.VirtualizationMode` 添付プロパティを <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> に設定して、スクロール中のパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="c88b1-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="c88b1-108">コード</span><span class="sxs-lookup"><span data-stu-id="c88b1-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="c88b1-109">次の例は、前の例で使用するデータを示しています。</span><span class="sxs-lookup"><span data-stu-id="c88b1-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
