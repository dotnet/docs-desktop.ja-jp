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
# <a name="how-to-use-a-grid-for-automatic-layout"></a>方法: 自動レイアウト用のグリッドを使用する
この例では、自動レイアウトの方法でグリッドを使用して、ローカライズ可能なアプリケーションを作成する方法について説明します。  
  
 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] のローカライズには時間がかかる場合があります。 多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要もあります。 これまでは、[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] が変更された言語ごとに調整する必要がありました。 現在では、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の機能で、調整する必要性の少ない要素をデザインできるようになりました。 サイズ変更や位置変更が簡単になるアプリケーションの作成方法は、`auto layout` と呼ばれます。  
  
 次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、グリッドを使用してボタンとテキストを配置する方法を示しています。 セルの高さと幅は `Auto` に設定されているため、イメージ付きのボタンを含むセルは、イメージに合わせて調整されることにご注意ください。 <xref:System.Windows.Controls.Grid> 要素はそのコンテンツに合わせて調整できるため、ローカライズ可能なアプリケーションの設計に、自動レイアウトを取得する場合に便利です。  
  
## <a name="example"></a>例  
 次の例では、グリッドを使用する方法を示します。  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 次の図は、コード サンプルの出力を示しています。  
  
 ![グリッドの例](./media/glob-grid.png "glob_grid")  
グリッド  
  
## <a name="see-also"></a>関連項目

- [自動レイアウトの使用の概要](use-automatic-layout-overview.md)
- [自動レイアウトを使用してボタンを作成する](how-to-use-automatic-layout-to-create-a-button.md)
