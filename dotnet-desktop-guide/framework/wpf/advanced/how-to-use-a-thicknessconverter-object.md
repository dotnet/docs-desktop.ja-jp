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
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="ca705-102">方法: ThicknessConverter オブジェクトを使用する</span><span class="sxs-lookup"><span data-stu-id="ca705-102">How to: Use a ThicknessConverter Object</span></span>

## <a name="example"></a><span data-ttu-id="ca705-103">例</span><span class="sxs-lookup"><span data-stu-id="ca705-103">Example</span></span>  

 <span data-ttu-id="ca705-104">この例では、<xref:System.Windows.ThicknessConverter> のインスタンスを作成し、それを使用して境界線の太さを変更する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ca705-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="ca705-105">この例では、`changeThickness` という名前のカスタム メソッドを定義します。このメソッドでは、別の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルで定義されている <xref:System.Windows.Controls.ListBoxItem> のコンテンツを、まず <xref:System.Windows.Thickness> のインスタンスに変換し、その後、そのコンテンツを <xref:System.String> に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca705-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="ca705-106">このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> を <xref:System.Windows.ThicknessConverter> オブジェクトに渡します。これにより、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.Windows.Thickness> のインスタンスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca705-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="ca705-107">次に、この値は、<xref:System.Windows.Controls.Border> の <xref:System.Windows.Controls.Border.BorderThickness%2A> プロパティの値として渡されます。</span><span class="sxs-lookup"><span data-stu-id="ca705-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="ca705-108">この例は実行できません。</span><span class="sxs-lookup"><span data-stu-id="ca705-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ca705-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca705-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="ca705-110">[方法: Margin プロパティを変更する](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ca705-110">[How to: Change the Margin Property](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="ca705-111">[方法: ListBoxItem を新しいデータ型に変換する](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ca705-111">[How to: Convert a ListBoxItem to a new Data Type](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="ca705-112">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="ca705-112">Panels Overview</span></span>](../controls/panels-overview.md)
