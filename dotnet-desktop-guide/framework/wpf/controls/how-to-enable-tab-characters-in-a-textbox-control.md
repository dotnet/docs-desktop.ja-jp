---
title: '方法: TextBox コントロールでタブ文字を有効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: 9a01ae93d1b75c604fbe4f15f720e0a84086bd1a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984347"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a><span data-ttu-id="5f501-102">方法: TextBox コントロールでタブ文字を有効にする</span><span class="sxs-lookup"><span data-stu-id="5f501-102">How to: Enable Tab Characters in a TextBox Control</span></span>
<span data-ttu-id="5f501-103">この例からは、<xref:System.Windows.Controls.TextBox> コントロールの通常の入力としてタブ文字を受け取る方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="5f501-103">This example shows how to enable the acceptance of tab characters as normal input in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f501-104">例</span><span class="sxs-lookup"><span data-stu-id="5f501-104">Example</span></span>  
 <span data-ttu-id="5f501-105"><xref:System.Windows.Controls.TextBox> コントロールの入力としてタブ文字を受け取るには、<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> 属性を **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f501-105">To enable the acceptance of tab characters as input in a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a><span data-ttu-id="5f501-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f501-106">See also</span></span>

- [<span data-ttu-id="5f501-107">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="5f501-107">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="5f501-108">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="5f501-108">RichTextBox Overview</span></span>](richtextbox-overview.md)
