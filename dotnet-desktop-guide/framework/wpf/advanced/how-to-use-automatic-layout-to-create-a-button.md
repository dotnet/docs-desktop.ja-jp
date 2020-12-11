---
title: '方法: 自動レイアウトを使用してボタンを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 05b874f9894841d3c318ee131d15165111fd596a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982060"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="96eec-102">方法: 自動レイアウトを使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="96eec-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="96eec-103">この例では、自動レイアウトの方法を使用して、ローカライズ可能なアプリケーションにボタンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96eec-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="96eec-104">[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] のローカライズには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="96eec-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="96eec-105">多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="96eec-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="96eec-106">これまでは、[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] が変更された言語ごとに調整する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="96eec-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="96eec-107">現在では、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の機能で、調整する必要性の少ない要素をデザインできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="96eec-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="96eec-108">サイズ変更や位置変更が簡単になるアプリケーションの作成方法は、`automatic layout` と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="96eec-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96eec-109">例</span><span class="sxs-lookup"><span data-stu-id="96eec-109">Example</span></span>  

<span data-ttu-id="96eec-110">次の 2 つの [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、ボタンをインスタンス化するアプリケーションを作成します。1 つは英語のテキストを使用し、もう 1 つはスペイン語のテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="96eec-110">The following two [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="96eec-111">テキストを除き、コードは同じであることに注目してください。ボタンがテキストに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="96eec-111">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="96eec-112">次の図は、コード サンプルの出力と自動でサイズが変更されるボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="96eec-112">The following graphic shows the output of the code samples with auto-resizable buttons:</span></span>
  
 ![テキストの言語が異なる同じボタン](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a><span data-ttu-id="96eec-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="96eec-114">See also</span></span>

- [<span data-ttu-id="96eec-115">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="96eec-115">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="96eec-116">自動レイアウト用のグリッドを使用する</span><span class="sxs-lookup"><span data-stu-id="96eec-116">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
