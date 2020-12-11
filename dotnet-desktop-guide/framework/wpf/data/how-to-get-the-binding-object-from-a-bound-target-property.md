---
title: '方法: バインドされているターゲット プロパティからのバインディング オブジェクトの取得'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985804"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="055e1-102">方法: バインドされているターゲット プロパティからのバインディング オブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="055e1-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="055e1-103">この例では、データにバインドされているターゲット プロパティからバインディング オブジェクトを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="055e1-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>

## <a name="example"></a><span data-ttu-id="055e1-104">例</span><span class="sxs-lookup"><span data-stu-id="055e1-104">Example</span></span>
 <span data-ttu-id="055e1-105">次のようにして、<xref:System.Windows.Data.Binding> オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="055e1-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> <span data-ttu-id="055e1-106">ターゲット オブジェクトの複数のプロパティがデータ バインディングを使用している可能性があるため、バインディングの依存関係プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="055e1-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>

 <span data-ttu-id="055e1-107">または、<xref:System.Windows.Data.BindingExpression> を取得してから、<xref:System.Windows.Data.BindingExpression.ParentBinding%2A> プロパティの値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="055e1-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>

 <span data-ttu-id="055e1-108">コード例全体については、「[バインディングの検証のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="055e1-108">For the complete example see [Binding Validation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>

> [!NOTE]
> <span data-ttu-id="055e1-109">バインディングが <xref:System.Windows.Data.MultiBinding> である場合は、<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="055e1-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="055e1-110"><xref:System.Windows.Data.PriorityBinding> の場合は、<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="055e1-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="055e1-111">ターゲット プロパティが、<xref:System.Windows.Data.Binding>、<xref:System.Windows.Data.MultiBinding>、<xref:System.Windows.Data.PriorityBinding> のどれを使用してバインドされているかが不明な場合は、<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="055e1-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="055e1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="055e1-112">See also</span></span>

- [<span data-ttu-id="055e1-113">コードでバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="055e1-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="055e1-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="055e1-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
