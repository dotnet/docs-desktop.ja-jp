---
title: '方法: ハイパーリンクに下線を引くかどうかを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 5718912e24a0697f209669b0ab4e7f4df1765ed3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974869"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="12379-102">方法: ハイパーリンクに下線を引くかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="12379-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="12379-103"><xref:System.Windows.Documents.Hyperlink> オブジェクトは、フロー コンテンツにハイパーリンクをホストする、インライン レベルのフロー コンテンツ要素です。</span><span class="sxs-lookup"><span data-stu-id="12379-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="12379-104"><xref:System.Windows.Documents.Hyperlink> は既定で <xref:System.Windows.TextDecoration> オブジェクトを使用して下線を表示します。</span><span class="sxs-lookup"><span data-stu-id="12379-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="12379-105">特に <xref:System.Windows.Documents.Hyperlink> オブジェクトの数が多い <xref:System.Windows.TextDecoration> オブジェクトのインスタンス化には、大きな負荷がかかります。</span><span class="sxs-lookup"><span data-stu-id="12379-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="12379-106"><xref:System.Windows.Documents.Hyperlink> 要素を多数使用する場合は、<xref:System.Windows.ContentElement.MouseEnter> イベントなどのイベントがトリガーされるときにのみ下線を表示することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="12379-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="12379-107">次の例では、"My MSN" リンクの下線は、<xref:System.Windows.ContentElement.MouseEnter> イベントがトリガーされたときにだけ表示される動的なものです。</span><span class="sxs-lookup"><span data-stu-id="12379-107">In the following example, the underline for the "My MSN" link is dynamic, that is, it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
  ![TextDecorations を表示するハイパーリンク](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  

## <a name="example"></a><span data-ttu-id="12379-109">例</span><span class="sxs-lookup"><span data-stu-id="12379-109">Example</span></span>  
 <span data-ttu-id="12379-110">次のマークアップ サンプルでは、下線ありとなしで定義された <xref:System.Windows.Documents.Hyperlink> を示しています。</span><span class="sxs-lookup"><span data-stu-id="12379-110">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="12379-111">次のコード サンプルでは、<xref:System.Windows.ContentElement.MouseEnter> イベントで <xref:System.Windows.Documents.Hyperlink> に下線を作成し、<xref:System.Windows.ContentElement.MouseLeave> イベントで削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="12379-111">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="12379-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="12379-112">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="12379-113">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="12379-113">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="12379-114">文字の装飾を作成する</span><span class="sxs-lookup"><span data-stu-id="12379-114">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)
