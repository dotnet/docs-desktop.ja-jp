---
title: '方法: バインドされた項目の一覧に基づいて値を生成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: ab030fbf4335a5bfd12834cb7b19c280487dc2f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974653"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>方法: バインドされた項目の一覧に基づいて値を生成する
<xref:System.Windows.Data.MultiBinding> を使用すると、ソース プロパティの一覧にバインディング ターゲット プロパティをバインドし、指定した入力で値を生成するロジックを適用することができます。 この例では、<xref:System.Windows.Data.MultiBinding> の使用方法を示します。  
  
## <a name="example"></a>例  
 次の例では、`NameListData` は、`PersonName` オブジェクトのコレクションを参照します。このオブジェクトは、`firstName` と `lastName` の 2 つのプロパティを含みます。 個人の氏名を姓から先に表示する <xref:System.Windows.Controls.TextBlock> を生成する例を次に示します。  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 姓が先の形式を生成する方法を理解するには、次に示す `NameConverter` の実装をご覧ください。  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` は、<xref:System.Windows.Data.IMultiValueConverter> インターフェイスを実装します。 `NameConverter` は、個々のバインディングから値を受け取り、それらを値のオブジェクト配列に格納します。 <xref:System.Windows.Data.Binding> 要素が <xref:System.Windows.Data.MultiBinding> 要素の下に表示される順序は、値が配列内に格納されている順序です。 <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 属性の値は、名前の形式を決定するパラメーターの切り替えを実行する <xref:System.Windows.Data.MultiBinding.Converter%2A> メソッドのパラメーター引数によって参照されます。  
  
## <a name="see-also"></a>関連項目

- [バインドされたデータを変換する](how-to-convert-bound-data.md)
- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
