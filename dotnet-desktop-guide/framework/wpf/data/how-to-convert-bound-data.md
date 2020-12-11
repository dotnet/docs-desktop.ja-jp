---
title: '方法: バインドされたデータを変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 981994426afd173fa8560d3ee24c6cf24c0c24aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983884"
---
# <a name="how-to-convert-bound-data"></a>方法: バインドされたデータを変換する
この例では、バインドで使用されるデータに変換を適用する方法を示します。  
  
 バインドの間にデータを変換するには、<xref:System.Windows.Data.IValueConverter> インターフェイスを実装するクラスを作成する必要があります。これには、<xref:System.Windows.Data.IValueConverter.Convert%2A> メソッドと <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> メソッドが含まれます。  
  
## <a name="example"></a>例  
 次の例では、渡された日付値を年、月、日のみが表示されるように変換する日付コンバーターの実装を示します。 <xref:System.Windows.Data.IValueConverter> インターフェイスを実装する場合、次の例のように、実装を <xref:System.Windows.Data.ValueConversionAttribute> 属性で装飾し、変換に関係するデータ型を開発ツールに示すのがよい方法です。  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 コンバーターを作成した後は、それをリソースとして [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルに追加できます。 次の例では、*src* を、*DateConverter* が定義されている名前空間にマップしています。  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 最後に、次の構文を使用して、バインドでコンバーターを使用できます。 次の例では、<xref:System.Windows.Controls.TextBlock> のテキストの内容が、外部データ ソースのプロパティである *StartDate* にバインドされています。  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 上の例で参照されているスタイル リソースは、このトピックでは示されていないリソース セクションで定義されています。  
  
## <a name="see-also"></a>関連項目

- [バインディングの検証の実装](how-to-implement-binding-validation.md)
- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
