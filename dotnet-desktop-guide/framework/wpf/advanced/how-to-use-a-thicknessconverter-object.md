---
title: '方法: ThicknessConverter オブジェクトを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 7420824ad939012d12f61ecbb72f2d00ce483e8b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982067"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>方法: ThicknessConverter オブジェクトを使用する

## <a name="example"></a>例  

 この例では、<xref:System.Windows.ThicknessConverter> のインスタンスを作成し、それを使用して境界線の太さを変更する方法を説明します。  
  
 この例では、`changeThickness` という名前のカスタム メソッドを定義します。このメソッドでは、別の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルで定義されている <xref:System.Windows.Controls.ListBoxItem> のコンテンツを、まず <xref:System.Windows.Thickness> のインスタンスに変換し、その後、そのコンテンツを <xref:System.String> に変換します。 このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> を <xref:System.Windows.ThicknessConverter> オブジェクトに渡します。これにより、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.Windows.Thickness> のインスタンスに変換されます。 次に、この値は、<xref:System.Windows.Controls.Border> の <xref:System.Windows.Controls.Border.BorderThickness%2A> プロパティの値として渡されます。  
  
 この例は実行できません。  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [方法: Margin プロパティを変更する](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))
- [方法: ListBoxItem を新しいデータ型に変換する](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))
- [パネルの概要](../controls/panels-overview.md)
