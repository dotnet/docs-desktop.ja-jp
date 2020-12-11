---
title: '方法: Freezable を読み取り専用にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: b8dcbec18977d46bd47b82f528deb2eeccc4e441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983276"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="10a6d-102">方法: Freezable を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="10a6d-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="10a6d-103">この例では、<xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出して <xref:System.Windows.Freezable> を読み取り専用にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="10a6d-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="10a6d-104">オブジェクトについて次のいずれかの条件が `true` の場合、<xref:System.Windows.Freezable> オブジェクトを凍結することはできません。</span><span class="sxs-lookup"><span data-stu-id="10a6d-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="10a6d-105">アニメーション化されたプロパティまたはデータ バインドされたプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="10a6d-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="10a6d-106">動的リソースによって設定されるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="10a6d-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="10a6d-107">動的リソースの詳細については、[XAML リソース](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10a6d-107">For more information about dynamic resources, see the [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>  
  
- <span data-ttu-id="10a6d-108">凍結できない <xref:System.Windows.Freezable> サブオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="10a6d-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="10a6d-109"><xref:System.Windows.Freezable> オブジェクトに対して、これらの条件が `false` であり、このオブジェクトを変更する予定がない場合は、パフォーマンスを向上させるために凍結させることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="10a6d-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a6d-110">例</span><span class="sxs-lookup"><span data-stu-id="10a6d-110">Example</span></span>  
 <span data-ttu-id="10a6d-111">次の例では、<xref:System.Windows.Freezable> オブジェクトの型である <xref:System.Windows.Media.SolidColorBrush> を凍結します。</span><span class="sxs-lookup"><span data-stu-id="10a6d-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="10a6d-112"><xref:System.Windows.Freezable> オブジェクトの詳細については、「[Freezable オブジェクトの概要](freezable-objects-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10a6d-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a6d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="10a6d-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="10a6d-114">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="10a6d-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="10a6d-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="10a6d-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
