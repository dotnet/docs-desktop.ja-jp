---
title: '方法 : 読み込まれたイベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 7ca95e195792f8fb4789c481e84dda51f2910434
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982091"
---
# <a name="how-to-handle-a-loaded-event"></a>方法 : 読み込まれたイベントを処理する
この例では、イベントを処理する方法 <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> と、そのイベントを処理するための適切なシナリオを示します。 ハンドラーは、 <xref:System.Windows.Controls.Button> ページが読み込まれるときにを作成します。  
  
## <a name="example"></a>例  
 次の例では、 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 分離コードファイルと共にを使用します。  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.FrameworkElement>
- [オブジェクトの有効期間イベント](object-lifetime-events.md)
- [ルーティング イベントの概要](routed-events-overview.md)
- [方法トピック](base-elements-how-to-topics.md)
