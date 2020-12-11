---
title: '方法: GroupBox テンプレートを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: f04e4a7e3feb4bd7c5dac1b4127d48923fb7ea62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985147"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="d112e-102">方法: GroupBox テンプレートを定義する</span><span class="sxs-lookup"><span data-stu-id="d112e-102">How to: Define a GroupBox Template</span></span>

<span data-ttu-id="d112e-103">この例では、<xref:System.Windows.Controls.GroupBox> コントロールのテンプレートを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d112e-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d112e-104">例</span><span class="sxs-lookup"><span data-stu-id="d112e-104">Example</span></span>  

 <span data-ttu-id="d112e-105">次の例では、レイアウトに <xref:System.Windows.Controls.Grid> コントロールを使用することで <xref:System.Windows.Controls.GroupBox> コントロール テンプレートが定義されています。</span><span class="sxs-lookup"><span data-stu-id="d112e-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="d112e-106">境界によって <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> コンテンツが隠されないよう、このテンプレートでは <xref:System.Windows.Controls.BorderGapMaskConverter> を使用して <xref:System.Windows.Controls.GroupBox> の境界が定義されます。</span><span class="sxs-lookup"><span data-stu-id="d112e-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="d112e-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="d112e-107">See also</span></span>

- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="d112e-108">[方法: GroupBox を作成する](/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d112e-108">[How to: Create a GroupBox](/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>
