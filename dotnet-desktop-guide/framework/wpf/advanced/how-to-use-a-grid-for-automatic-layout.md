---
title: '方法: 自動レイアウト用のグリッドを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 5389d8d6130367d36a5c81b3bdc316c989474ce2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982075"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="8d21b-102">方法: 自動レイアウト用のグリッドを使用する</span><span class="sxs-lookup"><span data-stu-id="8d21b-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="8d21b-103">この例では、自動レイアウトの方法でグリッドを使用して、ローカライズ可能なアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d21b-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="8d21b-104">[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] のローカライズには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d21b-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="8d21b-105">多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8d21b-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="8d21b-106">これまでは、[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] が変更された言語ごとに調整する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="8d21b-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="8d21b-107">現在では、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の機能で、調整する必要性の少ない要素をデザインできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8d21b-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="8d21b-108">サイズ変更や位置変更が簡単になるアプリケーションの作成方法は、`auto layout` と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8d21b-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="8d21b-109">次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、グリッドを使用してボタンとテキストを配置する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d21b-109">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="8d21b-110">セルの高さと幅は `Auto` に設定されているため、イメージ付きのボタンを含むセルは、イメージに合わせて調整されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="8d21b-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="8d21b-111"><xref:System.Windows.Controls.Grid> 要素はそのコンテンツに合わせて調整できるため、ローカライズ可能なアプリケーションの設計に、自動レイアウトを取得する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8d21b-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d21b-112">例</span><span class="sxs-lookup"><span data-stu-id="8d21b-112">Example</span></span>  
 <span data-ttu-id="8d21b-113">次の例では、グリッドを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8d21b-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="8d21b-114">次の図は、コード サンプルの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d21b-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="8d21b-115">![グリッドの例](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="8d21b-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="8d21b-116">グリッド</span><span class="sxs-lookup"><span data-stu-id="8d21b-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d21b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d21b-117">See also</span></span>

- [<span data-ttu-id="8d21b-118">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="8d21b-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="8d21b-119">自動レイアウトを使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="8d21b-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
