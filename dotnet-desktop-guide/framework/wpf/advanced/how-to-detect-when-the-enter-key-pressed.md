---
title: '方法: Enter キーが押されたことを検出する'
description: Windows Presentation Foundation でキーボードの Enter キーが選択されていることを検出します。 この例は、XAML と分離コード ファイルで構成されています。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: 1e74113f22e03f41da2e51178179aa52f6bfcd2c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983519"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>方法: Enter キーが押されたことを検出する
この例では、キーボードで <xref:System.Windows.Input.Key.Enter> キーが押されたことを検出する方法を示します。  
  
 この例は、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルと分離コード ファイルで構成されています。  
  
## <a name="example"></a>例  
 ユーザーが <xref:System.Windows.Controls.TextBox> で <xref:System.Windows.Input.Key.Enter> キーを押すと、テキスト ボックス内の入力が[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] の別の領域に表示されます。  
  
 次の XAML では、<xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.TextBlock>、および <xref:System.Windows.Controls.TextBox> で構成されるユーザー インターフェイスが作成されます。  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 次の分離コードでは、<xref:System.Windows.UIElement.KeyDown> イベント ハンドラーが作成されます。  押されたキーが <xref:System.Windows.Input.Key.Enter> キーの場合、<xref:System.Windows.Controls.TextBlock> にメッセージが表示されます。  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>関連項目

- [入力の概要](input-overview.md)
- [ルーティング イベントの概要](routed-events-overview.md)
