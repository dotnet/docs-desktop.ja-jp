---
title: '方法: ToolStripTextBox を拡大して ToolStrip の残りの幅に合わせる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982428"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="71ebb-102">方法 : ToolStripTextBox を拡大して ToolStrip の残りの幅に合わせる (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="71ebb-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="71ebb-103"><xref:System.Windows.Forms.ToolStrip.Stretch%2A>コントロールのプロパティをに設定すると、コントロールによって、コンテナーのサイズが変更さ <xref:System.Windows.Forms.ToolStrip> `true` れたときに、そのコンテナーが端から端に挿入され、サイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="71ebb-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="71ebb-104">この構成では、などのコントロールの項目を拡張して、 <xref:System.Windows.Forms.ToolStripTextBox> 使用可能な領域を塗りつぶすことや、コントロールのサイズを変更したときのサイズを変更することが役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="71ebb-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="71ebb-105">この拡大は、Microsoft® Internet Explorer のアドレスバーと同様の外観と動作を実現する場合などに便利です。</span><span class="sxs-lookup"><span data-stu-id="71ebb-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71ebb-106">例</span><span class="sxs-lookup"><span data-stu-id="71ebb-106">Example</span></span>  
 <span data-ttu-id="71ebb-107">次のコード例では、から派生したクラスを <xref:System.Windows.Forms.ToolStripTextBox> と呼び `ToolStripSpringTextBox` ます。</span><span class="sxs-lookup"><span data-stu-id="71ebb-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="71ebb-108">このクラスは、 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> <xref:System.Windows.Forms.ToolStrip> 他のすべての項目の合計幅が減算された後に、メソッドをオーバーライドして、親コントロールの使用可能な幅を計算します。</span><span class="sxs-lookup"><span data-stu-id="71ebb-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="71ebb-109">このコード例には、 <xref:System.Windows.Forms.Form> 新しい動作を示すクラスとクラスも用意されて `Program` います。</span><span class="sxs-lookup"><span data-stu-id="71ebb-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71ebb-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="71ebb-110">Compiling the Code</span></span>  
 <span data-ttu-id="71ebb-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71ebb-111">This example requires:</span></span>  
  
- <span data-ttu-id="71ebb-112">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="71ebb-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ebb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="71ebb-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="71ebb-114">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="71ebb-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="71ebb-115">方法: StatusStrip 内で Spring プロパティを対話的に使用する</span><span class="sxs-lookup"><span data-stu-id="71ebb-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
