---
title: '方法: ストーリーボードをシークする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: a57272c17a5bc6f5baaa21fb77233fc5693d1914
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981887"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="5a446-102">方法: ストーリーボードをシークする</span><span class="sxs-lookup"><span data-stu-id="5a446-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="5a446-103">次の例は、<xref:System.Windows.Media.Animation.Storyboard> の <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> メソッドを使用して、ストーリーボード アニメーション内の任意の位置にジャンプする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a446-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a446-104">例</span><span class="sxs-lookup"><span data-stu-id="5a446-104">Example</span></span>  
 <span data-ttu-id="5a446-105">サンプルの XAML マークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a446-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="5a446-106">例</span><span class="sxs-lookup"><span data-stu-id="5a446-106">Example</span></span>  
 <span data-ttu-id="5a446-107">上記の XAML コードと共に使用するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a446-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5a446-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a446-108">See also</span></span>

- [<span data-ttu-id="5a446-109">ストーリーボードを同期的にシークする</span><span class="sxs-lookup"><span data-stu-id="5a446-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
