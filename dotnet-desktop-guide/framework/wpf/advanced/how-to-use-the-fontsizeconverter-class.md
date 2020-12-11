---
title: '方法: FontSizeConverter クラスを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: b4662ef60866150008d84f22de44852b65373282
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985192"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="8435d-102">方法: FontSizeConverter クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="8435d-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="8435d-103">例</span><span class="sxs-lookup"><span data-stu-id="8435d-103">Example</span></span>  
 <span data-ttu-id="8435d-104">この例では、<xref:System.Windows.FontSizeConverter> のインスタンスを作成し、それを使用してフォント サイズを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8435d-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="8435d-105">この例では、`changeSize` という名前のカスタム メソッドを定義します。このメソッドでは、別の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルで定義されている <xref:System.Windows.Controls.ListBoxItem> のコンテンツを <xref:System.Double> のインスタンスに変換し、その後で <xref:System.String> に変換します。</span><span class="sxs-lookup"><span data-stu-id="8435d-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="8435d-106">このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> を <xref:System.Windows.FontSizeConverter> オブジェクトに渡します。これにより、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.Double> のインスタンスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="8435d-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="8435d-107">次に、この値は、<xref:System.Windows.Controls.TextBlock> 要素の <xref:System.Windows.Controls.TextBlock.FontSize%2A> プロパティの値として返されます。</span><span class="sxs-lookup"><span data-stu-id="8435d-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="8435d-108">この例では、`changeFamily` という名前の 2 番目のカスタム メソッドも定義されています。</span><span class="sxs-lookup"><span data-stu-id="8435d-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="8435d-109">このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.String> に変換され、その値が <xref:System.Windows.Controls.TextBlock> 要素の <xref:System.Windows.Controls.TextBlock.FontFamily%2A> プロパティに渡されます。</span><span class="sxs-lookup"><span data-stu-id="8435d-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="8435d-110">この例は実行できません。</span><span class="sxs-lookup"><span data-stu-id="8435d-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8435d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8435d-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
