---
title: '方法: 読み取り専用の Freezable の書き込み可能なコピーを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985023"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="e6d5f-102">方法: 読み取り専用の Freezable の書き込み可能なコピーを取得する</span><span class="sxs-lookup"><span data-stu-id="e6d5f-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="e6d5f-103">この例では、<xref:System.Windows.Freezable.Clone%2A> メソッドを使用して、読み取り専用の <xref:System.Windows.Freezable> の書き込み可能なコピーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e6d5f-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="e6d5f-104"><xref:System.Windows.Freezable> オブジェクトを読み取り専用 ("固定") としてマークした後は、そのオブジェクトを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6d5f-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="e6d5f-105">ただし、<xref:System.Windows.Freezable.Clone%2A> メソッドを使用すると、固定オブジェクトの複製を作成して、それを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e6d5f-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6d5f-106">例</span><span class="sxs-lookup"><span data-stu-id="e6d5f-106">Example</span></span>  
 <span data-ttu-id="e6d5f-107">次の例では、<xref:System.Windows.Media.SolidColorBrush> の固定オブジェクトの変更可能な複製を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6d5f-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="e6d5f-108"><xref:System.Windows.Freezable> オブジェクトの詳細については、「[Freezable オブジェクトの概要](freezable-objects-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6d5f-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d5f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6d5f-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="e6d5f-110">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="e6d5f-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="e6d5f-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e6d5f-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
