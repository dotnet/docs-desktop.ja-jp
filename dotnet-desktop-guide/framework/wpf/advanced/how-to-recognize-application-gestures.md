---
title: '方法: アプリケーション ジェスチャを認識する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 647e7c9c1d785cebfdc362dc48511d865f3945dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985000"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="d8273-102">方法: アプリケーション ジェスチャを認識する</span><span class="sxs-lookup"><span data-stu-id="d8273-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="d8273-103">次の例からは、ユーザーが <xref:System.Windows.Controls.InkCanvas> で <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> ジェスチャをしたときにインクを消す方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="d8273-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="d8273-104">この例では、`inkCanvas1` という名称の <xref:System.Windows.Controls.InkCanvas> が XAML ファイルで宣言されているものと想定します。</span><span class="sxs-lookup"><span data-stu-id="d8273-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8273-105">例</span><span class="sxs-lookup"><span data-stu-id="d8273-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d8273-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8273-106">See also</span></span>

- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
