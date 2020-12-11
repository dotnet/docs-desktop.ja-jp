---
title: '方法: コントロールの背景にテキストを描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974184"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="6ea8e-102">方法: コントロールの背景にテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="6ea8e-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="6ea8e-103">テキスト文字列を <xref:System.Windows.Media.FormattedText> オブジェクトに変換し、そのオブジェクトをコントロールの <xref:System.Windows.Media.DrawingContext> に描画することにより、コントロールの背景にテキストを直接描画できます。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="6ea8e-104">また、この方法を使用して、<xref:System.Windows.Controls.Canvas> や <xref:System.Windows.Controls.StackPanel> などの <xref:System.Windows.Controls.Panel> から派生したオブジェクトの背景に描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="6ea8e-105">![テキストを背景として表示するコントロールのスクリーンショット。](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="6ea8e-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="6ea8e-106">カスタム テキスト背景のコントロールの例</span><span class="sxs-lookup"><span data-stu-id="6ea8e-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ea8e-107">例</span><span class="sxs-lookup"><span data-stu-id="6ea8e-107">Example</span></span>  
 <span data-ttu-id="6ea8e-108">コントロールの背景に描画するには、新しい <xref:System.Windows.Media.DrawingBrush> オブジェクトを作成して、変換したテキストをオブジェクトの <xref:System.Windows.Media.DrawingContext> に描画します。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="6ea8e-109">次に、新しい <xref:System.Windows.Media.DrawingBrush> をコントロールの Background プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="6ea8e-110">次のコード例は、<xref:System.Windows.Media.FormattedText> オブジェクトを作成し、<xref:System.Windows.Controls.Label> オブジェクトと <xref:System.Windows.Controls.Button> オブジェクトの背景に描画する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ea8e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ea8e-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="6ea8e-112">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="6ea8e-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
