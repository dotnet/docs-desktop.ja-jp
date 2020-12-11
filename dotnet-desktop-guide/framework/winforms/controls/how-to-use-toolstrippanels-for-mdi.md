---
title: '方法: ToolStripPanel を MDI で使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
ms.openlocfilehash: 9bc64af92fbff26798d1cffede983cbab7ba13da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982791"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a><span data-ttu-id="4adfe-102">方法: ToolStripPanel を MDI で使用する</span><span class="sxs-lookup"><span data-stu-id="4adfe-102">How to: Use ToolStripPanels for MDI</span></span>
<span data-ttu-id="4adfe-103"><xref:System.Windows.Forms.ToolStripPanel> では、<xref:System.Windows.Forms.ToolStripPanel.Join%2A> メソッドを使用することにより、マルチ ドキュメント インターフェイス (MDI) アプリケーションに柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="4adfe-103">The <xref:System.Windows.Forms.ToolStripPanel> provides flexibility for multiple-document interface (MDI) applications by using the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4adfe-104">例</span><span class="sxs-lookup"><span data-stu-id="4adfe-104">Example</span></span>  
 <span data-ttu-id="4adfe-105">次のコード例は、<xref:System.Windows.Forms.ToolStripPanel> コントロールを MDI で使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4adfe-105">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls for MDI.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4adfe-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4adfe-106">Compiling the Code</span></span>  
 <span data-ttu-id="4adfe-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4adfe-107">This example requires:</span></span>  
  
- <span data-ttu-id="4adfe-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="4adfe-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4adfe-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4adfe-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="4adfe-110">方法: ToolStripPanel を結合する</span><span class="sxs-lookup"><span data-stu-id="4adfe-110">How to: Join ToolStripPanels</span></span>](how-to-join-toolstrippanels.md)
