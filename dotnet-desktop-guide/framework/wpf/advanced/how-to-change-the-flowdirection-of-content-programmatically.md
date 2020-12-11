---
title: '方法: プログラムによってコンテンツの FlowDirection を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983388"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="419db-102">方法: プログラムによってコンテンツの FlowDirection を変更する</span><span class="sxs-lookup"><span data-stu-id="419db-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="419db-103">この例では、<xref:System.Windows.Controls.FlowDocumentReader> の <xref:System.Windows.FrameworkElement.FlowDirection%2A> プロパティをプログラムで変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="419db-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="419db-104">例</span><span class="sxs-lookup"><span data-stu-id="419db-104">Example</span></span>  
 <span data-ttu-id="419db-105">2 つの <xref:System.Windows.Controls.Button> 要素が作成され、それぞれが <xref:System.Windows.FlowDirection> の使用できる値の 1 つを表します。</span><span class="sxs-lookup"><span data-stu-id="419db-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="419db-106">ボタンがクリックされると、関連付けられているプロパティ値が `tf1` という名前の <xref:System.Windows.Controls.FlowDocumentReader> のコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="419db-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="419db-107">プロパティ値は、`txt1` という名前の <xref:System.Windows.Controls.TextBlock> にも書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="419db-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="419db-108">例</span><span class="sxs-lookup"><span data-stu-id="419db-108">Example</span></span>  
 <span data-ttu-id="419db-109">上で定義されているボタン クリックに関連付けられているイベントは、C# 分離コード ファイルで処理されます。</span><span class="sxs-lookup"><span data-stu-id="419db-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
