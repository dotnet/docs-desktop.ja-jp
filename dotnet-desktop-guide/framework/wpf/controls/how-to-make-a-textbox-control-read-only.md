---
title: '方法: TextBox コントロールを読み取り専用にする'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 45fda33b5840bd89dac8d9e99f7dd1a8dd065838
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983891"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="3d165-102">方法: TextBox コントロールを読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="3d165-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="3d165-103">この例では、ユーザーの入力または変更を許可しないように、<xref:System.Windows.Controls.TextBox> コントロールを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d165-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d165-104">例</span><span class="sxs-lookup"><span data-stu-id="3d165-104">Example</span></span>  
 <span data-ttu-id="3d165-105">ユーザーが <xref:System.Windows.Controls.TextBox> コントロールのコンテンツを変更できないようにするには、<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 属性を **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3d165-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="3d165-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 属性は、ユーザー入力のみに影響します。<xref:System.Windows.Controls.TextBox> コントロールの [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 説明のテキスト セットや、<xref:System.Windows.Controls.TextBox.Text%2A> プロパティを使用してプログラムによって設定されたテキストに影響することはありません。</span><span class="sxs-lookup"><span data-stu-id="3d165-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="3d165-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> の既定値は **false** です。</span><span class="sxs-lookup"><span data-stu-id="3d165-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d165-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d165-108">See also</span></span>

- [<span data-ttu-id="3d165-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="3d165-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="3d165-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="3d165-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
