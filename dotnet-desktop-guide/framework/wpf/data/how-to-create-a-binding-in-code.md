---
title: '方法: コードでバインディングを作成する'
description: SetBinding メソッドを直接呼び出して、Windows Presentation Foundation アプリケーションのコードでバインディングを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: ed94118123823b4904896ddfbf2d5b429fc1012b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983883"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="8a05b-103">方法: コードでバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="8a05b-103">How to: Create a Binding in Code</span></span>

<span data-ttu-id="8a05b-104">この例では、コードで <xref:System.Windows.Data.Binding> を作成して設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8a05b-104">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a05b-105">例</span><span class="sxs-lookup"><span data-stu-id="8a05b-105">Example</span></span>  

 <span data-ttu-id="8a05b-106"><xref:System.Windows.FrameworkElement> クラスと <xref:System.Windows.FrameworkContentElement> クラスのどちらでも、`SetBinding` メソッドが公開されています。</span><span class="sxs-lookup"><span data-stu-id="8a05b-106">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="8a05b-107">これらのクラスのいずれかを継承する要素をバインドする場合は、<xref:System.Windows.FrameworkElement.SetBinding%2A> メソッドを直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8a05b-107">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="8a05b-108">次の例では、`MyDataProperty` という名前のプロパティが含まれる、`MyData` という名前のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a05b-108">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="8a05b-109">バインド オブジェクトを作成してバインドのソースを設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a05b-109">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="8a05b-110">この例では、<xref:System.Windows.FrameworkElement.SetBinding%2A> を使用して、<xref:System.Windows.Controls.TextBlock> コントロールである `myText` の <xref:System.Windows.Controls.TextBlock.Text%2A> プロパティを `MyDataProperty` にバインドします。</span><span class="sxs-lookup"><span data-stu-id="8a05b-110">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="8a05b-111">完全なコード サンプルについては、[コードのみのバインドのサンプル](/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a05b-111">For the complete code sample, see [Code-only Binding Sample](/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="8a05b-112"><xref:System.Windows.FrameworkElement.SetBinding%2A> を呼び出す代わりに、<xref:System.Windows.Data.BindingOperations> クラスの <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 静的メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a05b-112">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="8a05b-113">次の例では、<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> の代わりに <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> を呼び出して、`myText` を `myDataProperty` にバインドしています。</span><span class="sxs-lookup"><span data-stu-id="8a05b-113">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="8a05b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a05b-114">See also</span></span>

- [<span data-ttu-id="8a05b-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="8a05b-115">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8a05b-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8a05b-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
