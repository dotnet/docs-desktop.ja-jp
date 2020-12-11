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
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>方法: 自動レイアウトを使用してボタンを作成する
この例では、自動レイアウトの方法を使用して、ローカライズ可能なアプリケーションにボタンを作成する方法について説明します。  
  
 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] のローカライズには時間がかかる場合があります。 多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要があります。 これまでは、[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] が変更された言語ごとに調整する必要がありました。 現在では、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の機能で、調整する必要性の少ない要素をデザインできるようになりました。 サイズ変更や位置変更が簡単になるアプリケーションの作成方法は、`automatic layout` と呼ばれます。  
  
## <a name="example"></a>例  

次の 2 つの [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、ボタンをインスタンス化するアプリケーションを作成します。1 つは英語のテキストを使用し、もう 1 つはスペイン語のテキストを使用します。 テキストを除き、コードは同じであることに注目してください。ボタンがテキストに合わせて調整されます。

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 次の図は、コード サンプルの出力と自動でサイズが変更されるボタンを示しています。
  
 ![テキストの言語が異なる同じボタン](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a>関連項目

- [自動レイアウトの使用の概要](use-automatic-layout-overview.md)
- [自動レイアウト用のグリッドを使用する](how-to-use-a-grid-for-automatic-layout.md)
