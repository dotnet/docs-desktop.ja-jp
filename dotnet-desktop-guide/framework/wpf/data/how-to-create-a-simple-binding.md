---
title: '方法: 簡単なバインディングを作成する'
description: Windows Presentation Foundation (WPF) で、この操作方法の例を使用して、アプリケーションの簡単なバインディングを作成します。
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 9649116427c7da805323270fe3a23e6b23d330a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983880"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="0020c-103">方法: 簡単なバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="0020c-103">How to: Create a Simple Binding</span></span>
<span data-ttu-id="0020c-104">この例では、簡単な <xref:System.Windows.Data.Binding> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0020c-104">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0020c-105">例</span><span class="sxs-lookup"><span data-stu-id="0020c-105">Example</span></span>  
 <span data-ttu-id="0020c-106">この例では、`PersonName` という名前の文字列プロパティを持つ `Person` オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="0020c-106">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="0020c-107">`Person` オブジェクトは `SDKSample` という名前空間で定義されています。</span><span class="sxs-lookup"><span data-stu-id="0020c-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="0020c-108">次の例の `<src>` 要素を含む強調表示された行では、`PersonName` プロパティの値が `Joe` である `Person` オブジェクトがインスタンス化されています。</span><span class="sxs-lookup"><span data-stu-id="0020c-108">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="0020c-109">これは `Resources` セクションで行われ、`x:Key` が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0020c-109">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="0020c-110">`<TextBlock>` 要素を含む強調表示された行では、<xref:System.Windows.Controls.TextBlock> コントロールが `PersonName` プロパティにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="0020c-110">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="0020c-111">その結果、<xref:System.Windows.Controls.TextBlock> に "Joe" という値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0020c-111">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0020c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0020c-112">See also</span></span>

- [<span data-ttu-id="0020c-113">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="0020c-113">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="0020c-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="0020c-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
