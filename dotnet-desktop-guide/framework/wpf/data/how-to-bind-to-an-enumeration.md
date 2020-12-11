---
title: '方法: 列挙値にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: c92f1f00aa3feb37b70aa9a3647265236a1625b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974486"
---
# <a name="how-to-bind-to-an-enumeration"></a>方法: 列挙値にバインドする
この例では、列挙型の GetValues メソッドにバインドすることによって列挙型にバインドする方法を示します。  
  
## <a name="example"></a>例  
 次の例の <xref:System.Windows.Controls.ListBox> では、データ バインディングを通じて <xref:System.Windows.HorizontalAlignment> 列挙値の一覧が表示されます。 <xref:System.Windows.Controls.ListBox> と <xref:System.Windows.Controls.Button> は、<xref:System.Windows.Controls.ListBox> 内の値を選択することにより <xref:System.Windows.Controls.Button> の <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティ値を変更できるようにバインドされています。  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>関連項目

- [メソッドにバインドする](how-to-bind-to-a-method.md)
- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
