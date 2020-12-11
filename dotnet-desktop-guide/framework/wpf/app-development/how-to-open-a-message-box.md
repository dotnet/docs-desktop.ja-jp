---
title: '方法: メッセージ ボックスを開く'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984352"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="26cb8-102">方法: メッセージ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="26cb8-102">How to: Open a Message Box</span></span>
<span data-ttu-id="26cb8-103">この例では、メッセージ ボックスを開く方法を示します。</span><span class="sxs-lookup"><span data-stu-id="26cb8-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26cb8-104">例</span><span class="sxs-lookup"><span data-stu-id="26cb8-104">Example</span></span>  
 <span data-ttu-id="26cb8-105">メッセージ ボックスは、ユーザーに情報を表示するための作成済みのモーダル ダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="26cb8-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="26cb8-106">メッセージ ボックスを開くには、<xref:System.Windows.MessageBox> クラスの静的 <xref:System.Windows.MessageBox.Show%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="26cb8-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="26cb8-107"><xref:System.Windows.MessageBox.Show%2A> を呼び出すときに、文字列パラメーターを使用してメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="26cb8-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="26cb8-108"><xref:System.Windows.MessageBox.Show%2A> にはいくつかのオーバーロードがあり、メッセージ ボックスの表示方法を構成できます (「<xref:System.Windows.MessageBox>」を参照)。</span><span class="sxs-lookup"><span data-stu-id="26cb8-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="26cb8-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="26cb8-109">See also</span></span>

- [<span data-ttu-id="26cb8-110">MessageBox サンプル</span><span class="sxs-lookup"><span data-stu-id="26cb8-110">MessageBox Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
