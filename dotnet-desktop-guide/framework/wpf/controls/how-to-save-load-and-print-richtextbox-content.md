---
title: '方法: RichTextBox コンテンツの保存、読み込み、および印刷'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
ms.openlocfilehash: 90581bee7815dafd44c3cae18a8af7394fee1e9a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984888"
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="04e71-102">方法: RichTextBox コンテンツの保存、読み込み、および印刷</span><span class="sxs-lookup"><span data-stu-id="04e71-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="04e71-103">次の例では、<xref:System.Windows.Controls.RichTextBox> のコンテンツをファイルに保存し、そのコンテンツを <xref:System.Windows.Controls.RichTextBox> に再度読み込み、コンテンツを印刷する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="04e71-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04e71-104">例</span><span class="sxs-lookup"><span data-stu-id="04e71-104">Example</span></span>  
 <span data-ttu-id="04e71-105">この例のマークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="04e71-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="04e71-106">例</span><span class="sxs-lookup"><span data-stu-id="04e71-106">Example</span></span>  
 <span data-ttu-id="04e71-107">この例のコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="04e71-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="04e71-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="04e71-108">See also</span></span>

- [<span data-ttu-id="04e71-109">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="04e71-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="04e71-110">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="04e71-110">TextBox Overview</span></span>](textbox-overview.md)
