---
title: '方法: 分析のヒントに従ってインクを分析する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: 5e94628d357a2ca75ad1b6fb7e464a3355f1fd5f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982303"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="f042a-102">方法: 分析のヒントに従ってインクを分析する</span><span class="sxs-lookup"><span data-stu-id="f042a-102">How to: Analyze Ink with Analysis Hints</span></span>

<span data-ttu-id="f042a-103">[System.Windows.Ink.AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) では、それがアタッチされている [System.Windows.Ink.InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) にヒントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f042a-103">An [System.Windows.Ink.AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) provides a hint for the [System.Windows.Ink.InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) to which it is attached.</span></span>  <span data-ttu-id="f042a-104">このヒントは、[System.Windows.Ink.AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) の [System.Windows.Ink.ContextNode.Location%2A](/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) プロパティで指定した領域に適用され、インク アナライザーに追加のコンテキストを提供して認識精度を向上させます。</span><span class="sxs-lookup"><span data-stu-id="f042a-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) property of the [System.Windows.Ink.AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="f042a-105">このコンテンツ情報は、[System.Windows.Ink.InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) がヒント領域から得たインクを分析するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f042a-105">The [System.Windows.Ink.InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f042a-106">例</span><span class="sxs-lookup"><span data-stu-id="f042a-106">Example</span></span>  

 <span data-ttu-id="f042a-107">次の例では、フォームで [System.Windows.Ink.AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) オブジェクトが複数使用される、インク入力を取るアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="f042a-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objects on a form that accepts ink input.</span></span> <span data-ttu-id="f042a-108">このアプリケーションでは、[System.Windows.Ink.AnalysisHintNode.Factoid%2A](/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) プロパティを使用して、フォーム上の各エントリに対してコンテキスト情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f042a-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="f042a-109">このアプリケーションでは、バックグラウンド分析を使用してインクを分析し、ユーザーがインクの追加を停止してから 5 秒後にフォームからすべてのインクがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="f042a-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
