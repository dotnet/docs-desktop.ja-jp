---
title: '方法: Canvas のコンテンツを Border で囲む'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Canvas
- controls [WPF], Border
- Canvas control [WPF], wrapping with Border
- Border control [WPF], wrapping Canvas
ms.assetid: caf0404f-f4e7-484f-9928-5dae1238d8ef
ms.openlocfilehash: 5d33af798d2e626cea08fa71c9b2c88acb22b5e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983683"
---
# <a name="how-to-wrap-a-border-around-the-content-of-a-canvas"></a><span data-ttu-id="f93b1-102">方法: Canvas のコンテンツを Border で囲む</span><span class="sxs-lookup"><span data-stu-id="f93b1-102">How to: Wrap a Border Around the Content of a Canvas</span></span>
<span data-ttu-id="f93b1-103">この例は、<xref:System.Windows.Controls.Border> を使用して <xref:System.Windows.Controls.Canvas> 要素をラップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f93b1-103">This example shows how to wrap a <xref:System.Windows.Controls.Canvas> element with a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f93b1-104">例</span><span class="sxs-lookup"><span data-stu-id="f93b1-104">Example</span></span>  
 <span data-ttu-id="f93b1-105">次の例は、<xref:System.Windows.Controls.Canvas> 要素内での `Hello World!` の表示方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f93b1-105">The following example shows how to display `Hello World!` inside a <xref:System.Windows.Controls.Canvas> element.</span></span> <span data-ttu-id="f93b1-106"><xref:System.Windows.Controls.Canvas> 要素は、枠線によって要素のアウトラインが示されるように <xref:System.Windows.Controls.Border> 要素によってラップされています。</span><span class="sxs-lookup"><span data-stu-id="f93b1-106">The <xref:System.Windows.Controls.Canvas> element is wrapped by a <xref:System.Windows.Controls.Border> element so that a border outlines the element.</span></span>  
  
 [!code-xaml[CanvasHelloWorldBorder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasHelloWorldBorder/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f93b1-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="f93b1-107">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="f93b1-108">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="f93b1-108">Panels Overview</span></span>](panels-overview.md)
