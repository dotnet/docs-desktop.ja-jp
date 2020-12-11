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
# <a name="how-to-create-a-simple-binding"></a>方法: 簡単なバインディングを作成する
この例では、簡単な <xref:System.Windows.Data.Binding> を作成する方法を示します。  
  
## <a name="example"></a>例  
 この例では、`PersonName` という名前の文字列プロパティを持つ `Person` オブジェクトがあります。 `Person` オブジェクトは `SDKSample` という名前空間で定義されています。  
  
 次の例の `<src>` 要素を含む強調表示された行では、`PersonName` プロパティの値が `Joe` である `Person` オブジェクトがインスタンス化されています。 これは `Resources` セクションで行われ、`x:Key` が割り当てられます。  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 `<TextBlock>` 要素を含む強調表示された行では、<xref:System.Windows.Controls.TextBlock> コントロールが `PersonName` プロパティにバインドされます。 その結果、<xref:System.Windows.Controls.TextBlock> に "Joe" という値が表示されます。  
  
## <a name="see-also"></a>関連項目

- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
