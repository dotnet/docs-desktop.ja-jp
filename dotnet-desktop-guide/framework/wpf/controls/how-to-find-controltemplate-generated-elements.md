---
title: '方法: ControlTemplate によって生成された要素を検索する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 064f70835443accef83ca5f3d912ace861c2216a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975078"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>方法: ControlTemplate によって生成された要素を検索する
この例では、<xref:System.Windows.Controls.ControlTemplate> によって生成された要素を検索する方法を示します。  
  
## <a name="example"></a>例  
 次の例は、<xref:System.Windows.Controls.Button> クラスの単純な <xref:System.Windows.Controls.ControlTemplate> を作成するスタイルを示しています。  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 テンプレートが適用された後にテンプレート内の要素を検索するには、<xref:System.Windows.Controls.Control.Template%2A> の <xref:System.Windows.FrameworkTemplate.FindName%2A> メソッドを呼び出すことができます。 次の例は、コントロール テンプレート内の <xref:System.Windows.Controls.Grid> の実際の幅の値を示すメッセージ ボックスを作成しています。  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>関連項目

- [DataTemplate によって生成された要素を検索する](../data/how-to-find-datatemplate-generated-elements.md)
- [スタイルとテンプレート](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [WPF XAML 名前スコープ](../advanced/wpf-xaml-namescopes.md)
- [WPF のツリー](../advanced/trees-in-wpf.md)
