---
title: '方法: ドラッグされた GridView 列ヘッダーのスタイルを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984828"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="f25d7-102">方法: ドラッグされた GridView 列ヘッダーのスタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="f25d7-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="f25d7-103">この例からは、ユーザーが列の位置を変更するとき、ドラッグした <xref:System.Windows.Controls.GridViewColumnHeader> の外観を変更する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="f25d7-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f25d7-104">例</span><span class="sxs-lookup"><span data-stu-id="f25d7-104">Example</span></span>  
 <span data-ttu-id="f25d7-105">その表示モードに <xref:System.Windows.Controls.GridView> が使用される <xref:System.Windows.Controls.ListView> で列ヘッダーを別の場所にドラッグすると、列が新しい位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="f25d7-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="f25d7-106">列ヘッダーをドラッグしている間、元のヘッダー以外に、フロート状態のヘッダーのコピーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f25d7-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="f25d7-107"><xref:System.Windows.Controls.GridView> の列ヘッダーは <xref:System.Windows.Controls.GridViewColumnHeader> によって表されます。</span><span class="sxs-lookup"><span data-stu-id="f25d7-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="f25d7-108">このフロート状態と元のヘッダーの両方の外観をカスタマイズするには、<xref:System.Windows.Controls.ControlTemplate.Triggers%2A> を設定して <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style> を変更します。</span><span class="sxs-lookup"><span data-stu-id="f25d7-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="f25d7-109">これらの <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> は、<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> プロパティ値が `true` で、<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> プロパティ値が <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> のときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f25d7-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="f25d7-110">マウスが <xref:System.Windows.Controls.GridViewColumnHeader> の上にあるとき、ユーザーがマウス ボタンを押したままにすると、<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> プロパティ値が `true` に変わります。</span><span class="sxs-lookup"><span data-stu-id="f25d7-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="f25d7-111">同様に、ユーザーがドラッグ操作を開始すると、<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> プロパティが <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> に変わります。</span><span class="sxs-lookup"><span data-stu-id="f25d7-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="f25d7-112">次の例に、ユーザーが列を新しい位置にドラッグするときに、フロート状態と元のヘッダーの <xref:System.Windows.Controls.Control.Foreground%2A> 色と <xref:System.Windows.Controls.Control.Background%2A> 色を変えるように <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f25d7-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="f25d7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f25d7-113">See also</span></span>

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="f25d7-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f25d7-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="f25d7-115">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="f25d7-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="f25d7-116">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="f25d7-116">GridView Overview</span></span>](gridview-overview.md)
