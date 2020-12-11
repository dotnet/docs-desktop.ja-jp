---
title: '方法: グリッドの子要素を配置する'
description: Windows Presentation Foundation の Grid で定義されている get と set メソッドを使用して、子要素を配置する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985820"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>方法: グリッドの子要素を配置する
この例では、<xref:System.Windows.Controls.Grid> で定義されている get メソッドと set メソッドを使用して、子要素を配置する方法を示します。  
  
## <a name="example"></a>例  
 次の例では、3 つの列と 3 つの行を持つ親 <xref:System.Windows.Controls.Grid> 要素 (`grid1`) を定義します。 子 <xref:System.Windows.Shapes.Rectangle> 要素 (`rect1`) は、列位置 0、行位置 0 の <xref:System.Windows.Controls.Grid> に追加されます。 <xref:System.Windows.Controls.Button> 要素によって表されるメソッドを呼び出すことで、<xref:System.Windows.Controls.Grid> 内の <xref:System.Windows.Shapes.Rectangle> 要素の位置を変更できます。 ユーザーがボタンをクリックすると、関連するメソッドがアクティブ化されます。  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 次のコードビハインドの例では、ボタンの <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントが発生するメソッドが処理されています。 この例では、これらのメソッドの呼び出しが <xref:System.Windows.Controls.TextBlock> 要素に書き込まれ、そこで関連する get メソッドを使用して新しいプロパティ値が文字列として出力されます。  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 完成した結果を次に示します。

 ![2 つの列を持つ WPF ユーザー インターフェイスを示すスクリーンショット。右側には 3 × 3 のグリッドがあり、左側にはグリッドの列と行の間で色付きの四角形を移動するボタンがある](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.Grid>
- [パネルの概要](panels-overview.md)
