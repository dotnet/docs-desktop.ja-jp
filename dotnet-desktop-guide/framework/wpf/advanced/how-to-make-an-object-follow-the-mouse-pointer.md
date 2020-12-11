---
title: '方法: オブジェクトをマウス ポインターに追従させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: f348586341d0fa5b6e1a5fe15ab8c3a75e369e64
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983272"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="b8a53-102">方法: オブジェクトをマウス ポインターに追従させる</span><span class="sxs-lookup"><span data-stu-id="b8a53-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="b8a53-103">この例では、マウス ポインターが画面上を移動したときにオブジェクトのディメンションを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8a53-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="b8a53-104">この例には、[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] を作成する [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルと、イベント ハンドラーを作成する分離コード ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8a53-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a53-105">例</span><span class="sxs-lookup"><span data-stu-id="b8a53-105">Example</span></span>  
 <span data-ttu-id="b8a53-106">次の XAML では、<xref:System.Windows.Controls.StackPanel> 内の <xref:System.Windows.Shapes.Ellipse> で構成される [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] が作成され、<xref:System.Windows.UIElement.MouseMove> イベントのイベント ハンドラーがアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="b8a53-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="b8a53-107">次の分離コードでは、<xref:System.Windows.UIElement.MouseMove> イベント ハンドラーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8a53-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="b8a53-108">マウス ポインターを動かすと、<xref:System.Windows.Shapes.Ellipse> の高さと幅が増減します。</span><span class="sxs-lookup"><span data-stu-id="b8a53-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a53-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8a53-109">See also</span></span>

- [<span data-ttu-id="b8a53-110">入力の概要</span><span class="sxs-lookup"><span data-stu-id="b8a53-110">Input Overview</span></span>](input-overview.md)
