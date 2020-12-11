---
title: '方法: 論理ツリーをオーバーライドする'
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985020"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="05ed6-102">方法: 論理ツリーをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="05ed6-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="05ed6-103">ほとんどの場合は必要ありませんが、高度なコントロールを作成する場合は、必要に応じて論理ツリーをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="05ed6-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05ed6-104">例</span><span class="sxs-lookup"><span data-stu-id="05ed6-104">Example</span></span>  
 <span data-ttu-id="05ed6-105"><xref:System.Windows.Controls.StackPanel> をサブクラス化して論理ツリーをオーバーライドする方法を次の例に示します。この例では、パネルが子要素を 1 つだけ持つことができ、その子要素だけをレンダリングするという動作を強制的に適用しています。</span><span class="sxs-lookup"><span data-stu-id="05ed6-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="05ed6-106">これは実際的には必ずしも好ましい動作ではありませんが、ここでは要素の通常の論理ツリーをオーバーライドするシナリオを説明するための手段として示します。</span><span class="sxs-lookup"><span data-stu-id="05ed6-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="05ed6-107">論理ツリーについて詳しくは、「[WPF のツリー](trees-in-wpf.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="05ed6-107">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>
