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
# <a name="how-to-create-a-binding-in-code"></a>方法: コードでバインディングを作成する

この例では、コードで <xref:System.Windows.Data.Binding> を作成して設定する方法を示します。  
  
## <a name="example"></a>例  

 <xref:System.Windows.FrameworkElement> クラスと <xref:System.Windows.FrameworkContentElement> クラスのどちらでも、`SetBinding` メソッドが公開されています。 これらのクラスのいずれかを継承する要素をバインドする場合は、<xref:System.Windows.FrameworkElement.SetBinding%2A> メソッドを直接呼び出すことができます。  
  
 次の例では、`MyDataProperty` という名前のプロパティが含まれる、`MyData` という名前のクラスを作成します。  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 バインド オブジェクトを作成してバインドのソースを設定する方法の例を次に示します。  この例では、<xref:System.Windows.FrameworkElement.SetBinding%2A> を使用して、<xref:System.Windows.Controls.TextBlock> コントロールである `myText` の <xref:System.Windows.Controls.TextBlock.Text%2A> プロパティを `MyDataProperty` にバインドします。  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 完全なコード サンプルについては、[コードのみのバインドのサンプル](/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))に関する記事を参照してください。  
  
 <xref:System.Windows.FrameworkElement.SetBinding%2A> を呼び出す代わりに、<xref:System.Windows.Data.BindingOperations> クラスの <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 静的メソッドを使用できます。 次の例では、<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> の代わりに <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> を呼び出して、`myText` を `myDataProperty` にバインドしています。  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>関連項目

- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
