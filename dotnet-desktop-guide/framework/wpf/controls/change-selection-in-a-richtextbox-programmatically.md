---
title: プログラムによる RichTextBox での選択の変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: e3c76bd244e567857ebf132db5cc19c2d51139bd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984228"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="b939a-102">プログラムによる RichTextBox での選択の変更</span><span class="sxs-lookup"><span data-stu-id="b939a-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="b939a-103">この例では、<xref:System.Windows.Controls.RichTextBox> の現在の選択を、プログラムを使って変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b939a-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="b939a-104">この選択は、ユーザーがユーザー インターフェイスを使用してコンテンツを選択した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="b939a-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b939a-105">例</span><span class="sxs-lookup"><span data-stu-id="b939a-105">Example</span></span>  
 <span data-ttu-id="b939a-106">次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] コードでは、単純コンテンツが含まれる名前付き <xref:System.Windows.Controls.RichTextBox> コントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b939a-106">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="b939a-107">例</span><span class="sxs-lookup"><span data-stu-id="b939a-107">Example</span></span>  
 <span data-ttu-id="b939a-108">次のコードでは、ユーザーが <xref:System.Windows.Controls.RichTextBox> 内をクリックすると、任意のテキストがプログラムで選択されます。</span><span class="sxs-lookup"><span data-stu-id="b939a-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b939a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b939a-109">See also</span></span>

- [<span data-ttu-id="b939a-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="b939a-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="b939a-111">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="b939a-111">TextBox Overview</span></span>](textbox-overview.md)
