---
title: '方法: イベントを使用してロールオーバー効果を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d4587b7b116045af11702a99c841956434f96404
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984628"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="88b99-102">方法: イベントを使用してロールオーバー効果を作成する</span><span class="sxs-lookup"><span data-stu-id="88b99-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="88b99-103">この例では、マウス ポインターとしての要素の色を変更する方法を示し、その領域が要素で占有されたままにします。</span><span class="sxs-lookup"><span data-stu-id="88b99-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="88b99-104">この例は、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルと分離コード ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="88b99-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88b99-105">この例では、イベントを使用する方法を示していますが、これと同じ効果を得るには、スタイルで <xref:System.Windows.Trigger> を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="88b99-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="88b99-106">詳しくは、「 [スタイルとテンプレート](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88b99-106">For more information, see [Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88b99-107">例</span><span class="sxs-lookup"><span data-stu-id="88b99-107">Example</span></span>  
 <span data-ttu-id="88b99-108">次の XAML では、<xref:System.Windows.Controls.TextBlock> の周辺の <xref:System.Windows.Controls.Border> で構成されるユーザー インターフェイスを作成し、<xref:System.Windows.Input.Mouse.MouseEnter> イベント ハンドラーと <xref:System.Windows.UIElement.MouseLeave> イベント ハンドラーを <xref:System.Windows.Controls.Border> にアタッチします。</span><span class="sxs-lookup"><span data-stu-id="88b99-108">The following XAML creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="88b99-109">次の分離コードでは、<xref:System.Windows.UIElement.MouseEnter> および <xref:System.Windows.UIElement.MouseLeave> イベント ハンドラーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="88b99-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="88b99-110">マウス ポインターが <xref:System.Windows.Controls.Border> に入ると、<xref:System.Windows.Controls.Border> の背景が赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="88b99-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="88b99-111">マウス ポインターが <xref:System.Windows.Controls.Border> を出ると、<xref:System.Windows.Controls.Border> の背景が白に変更されます。</span><span class="sxs-lookup"><span data-stu-id="88b99-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
