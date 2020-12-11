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
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="0b57e-102">方法: バインドされたデータを変換する</span><span class="sxs-lookup"><span data-stu-id="0b57e-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="0b57e-103">この例では、バインドで使用されるデータに変換を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0b57e-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="0b57e-104">バインドの間にデータを変換するには、<xref:System.Windows.Data.IValueConverter> インターフェイスを実装するクラスを作成する必要があります。これには、<xref:System.Windows.Data.IValueConverter.Convert%2A> メソッドと <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b57e-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b57e-105">例</span><span class="sxs-lookup"><span data-stu-id="0b57e-105">Example</span></span>  
 <span data-ttu-id="0b57e-106">次の例では、渡された日付値を年、月、日のみが表示されるように変換する日付コンバーターの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="0b57e-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="0b57e-107"><xref:System.Windows.Data.IValueConverter> インターフェイスを実装する場合、次の例のように、実装を <xref:System.Windows.Data.ValueConversionAttribute> 属性で装飾し、変換に関係するデータ型を開発ツールに示すのがよい方法です。</span><span class="sxs-lookup"><span data-stu-id="0b57e-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="0b57e-108">コンバーターを作成した後は、それをリソースとして [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="0b57e-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="0b57e-109">次の例では、*src* を、*DateConverter* が定義されている名前空間にマップしています。</span><span class="sxs-lookup"><span data-stu-id="0b57e-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="0b57e-110">最後に、次の構文を使用して、バインドでコンバーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b57e-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="0b57e-111">次の例では、<xref:System.Windows.Controls.TextBlock> のテキストの内容が、外部データ ソースのプロパティである *StartDate* にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="0b57e-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="0b57e-112">上の例で参照されているスタイル リソースは、このトピックでは示されていないリソース セクションで定義されています。</span><span class="sxs-lookup"><span data-stu-id="0b57e-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b57e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b57e-113">See also</span></span>

- [<span data-ttu-id="0b57e-114">バインディングの検証の実装</span><span class="sxs-lookup"><span data-stu-id="0b57e-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="0b57e-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="0b57e-115">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="0b57e-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="0b57e-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
