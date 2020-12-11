---
title: '方法: Canvas の配置プロパティを取得または設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980467"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="00c56-102">方法: Canvas の配置プロパティを取得または設定する</span><span class="sxs-lookup"><span data-stu-id="00c56-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="00c56-103">この例からは、<xref:System.Windows.Controls.Canvas> 要素の配置メソッドを利用し、子コンテンツを配置する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="00c56-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="00c56-104">この例では、<xref:System.Windows.Controls.ListBoxItem> のコンテンツを利用して配置値を表し、値を <xref:System.Double> のインスタンスに変換しています。このインスタンスは、配置に必須の引数です。</span><span class="sxs-lookup"><span data-stu-id="00c56-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="00c56-105">値はその後、文字列に再変換され、<xref:System.Windows.Controls.Canvas.GetLeft%2A> メソッドを利用することで <xref:System.Windows.Controls.TextBlock> 要素にテキストとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="00c56-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c56-106">例</span><span class="sxs-lookup"><span data-stu-id="00c56-106">Example</span></span>  
 <span data-ttu-id="00c56-107">次の例では、選択できる <xref:System.Windows.Controls.ListBoxItem> 要素が 11 ある <xref:System.Windows.Controls.ListBox> 要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="00c56-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="00c56-108"><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> イベントによって `ChangeLeft` カスタム メソッドがトリガーされます。これは、後続のコード ブロックによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="00c56-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="00c56-109">各 <xref:System.Windows.Controls.ListBoxItem> によって <xref:System.Double> が表されます。これは、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Canvas.SetLeft%2A> メソッドで受け取られる引数の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="00c56-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="00c56-110"><xref:System.Windows.Controls.ListBoxItem> を利用して <xref:System.Double> のインスタンスを表すには、まず、正しいデータ型に <xref:System.Windows.Controls.ListBoxItem> を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00c56-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="00c56-111">ユーザーが <xref:System.Windows.Controls.ListBox> 選択を変更すると、`ChangeLeft` カスタム メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="00c56-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="00c56-112">このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> が <xref:System.Windows.LengthConverter> オブジェクトに渡されます。このオブジェクトによって、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.Double> のインスタンスに変換されます (この値は、<xref:System.Windows.Controls.Control.ToString%2A> メソッドを利用することで <xref:System.String> に既に変換されていることに注目してください)。</span><span class="sxs-lookup"><span data-stu-id="00c56-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="00c56-113">この値は次に、`text1` オブジェクトの位置を変更するため、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Canvas.SetLeft%2A> メソッドと <xref:System.Windows.Controls.Canvas.GetLeft%2A> メソッドに戻されます。</span><span class="sxs-lookup"><span data-stu-id="00c56-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="00c56-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="00c56-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="00c56-115">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="00c56-115">Panels Overview</span></span>](panels-overview.md)
