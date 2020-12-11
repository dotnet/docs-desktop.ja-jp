---
title: '方法: ColumnDefinitionsCollections および RowDefinitionsCollections を使用して列と行を操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 2f6d174fd54dca3744e5967f198c645e01a94fe5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984100"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="cd025-102">方法: ColumnDefinitionsCollections および RowDefinitionsCollections を使用して列と行を操作する</span><span class="sxs-lookup"><span data-stu-id="cd025-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="cd025-103">この例では、<xref:System.Windows.Controls.ColumnDefinitionCollection> クラスと <xref:System.Windows.Controls.RowDefinitionCollection> クラスのメソッドを使用して、行または列のコンテンツの追加、クリア、カウントなどの操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cd025-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="cd025-104">たとえば、<xref:System.Windows.Controls.ColumnDefinition> または <xref:System.Windows.Controls.RowDefinition> に含まれる項目を <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>、<xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>、または <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> できます。</span><span class="sxs-lookup"><span data-stu-id="cd025-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd025-105">例</span><span class="sxs-lookup"><span data-stu-id="cd025-105">Example</span></span>  
 <span data-ttu-id="cd025-106">次の例では、`grid1` という <xref:System.Windows.FrameworkElement.Name%2A> を持つ <xref:System.Windows.Controls.Grid> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="cd025-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="cd025-107"><xref:System.Windows.Controls.Grid> には、<xref:System.Windows.Controls.Button> 要素を保持する <xref:System.Windows.Controls.StackPanel> が含まれており、異なるコレクションメソッドによってそれぞれが制御されます。</span><span class="sxs-lookup"><span data-stu-id="cd025-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="cd025-108"><xref:System.Windows.Controls.Button> をクリックすると、分離コード ファイル内のメソッド呼び出しがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="cd025-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="cd025-109">この例では、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイル内の <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントに対応する一連のカスタム メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd025-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="cd025-110"><xref:System.Windows.Controls.Grid> の列と行の数を変更するには、行や列の追加や削除など、いくつかの方法があり、行と列の合計数をカウントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cd025-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="cd025-111"><xref:System.ArgumentOutOfRangeException> と <xref:System.ArgumentException> の例外を回避するには、<xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> メソッドが提供するエラー チェック機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd025-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cd025-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd025-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
