---
title: '方法: TextBox から行のコレクションを取得する'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984340"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="a81de-102">方法: TextBox から行のコレクションを取得する</span><span class="sxs-lookup"><span data-stu-id="a81de-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="a81de-103">次の例では、<xref:System.Windows.Controls.TextBox> から一連のテキスト行を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a81de-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a81de-104">例</span><span class="sxs-lookup"><span data-stu-id="a81de-104">Example</span></span>  
 <span data-ttu-id="a81de-105">次の例では、引数として <xref:System.Windows.Controls.TextBox> を受け取り、**TextBox** にテキスト行が含まれる <xref:System.Collections.Specialized.StringCollection> を返す単純なメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="a81de-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="a81de-106"><xref:System.Windows.Controls.TextBox.LineCount%2A> プロパティは、**TextBox** に現在含まれている行の数を決定するために使用されます。その後、各行を抽出し、それを行のコレクションに追加するために <xref:System.Windows.Controls.TextBox.GetLineText%2A> メソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a81de-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="a81de-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="a81de-107">See also</span></span>

- [<span data-ttu-id="a81de-108">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="a81de-108">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="a81de-109">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="a81de-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
