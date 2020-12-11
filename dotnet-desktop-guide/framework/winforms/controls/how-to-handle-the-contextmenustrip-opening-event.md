---
title: '方法: ContextMenuStrip のオープン イベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982112"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>方法: ContextMenuStrip のオープン イベントを処理する
イベントを処理することによって、コントロールの動作をカスタマイズでき <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripDropDown.Opening> ます。  
  
## <a name="example"></a>例  
 イベントを処理する方法を次のコード例に示し <xref:System.Windows.Forms.ToolStripDropDown.Opening> ます。 イベントハンドラーは、コントロールに項目を動的に追加し <xref:System.Windows.Forms.ContextMenuStrip> ます。 完全なコード例については、「 [方法: ToolStrip 項目を動的に追加する](how-to-add-toolstrip-items-dynamically.md)」を参照してください。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> `true` メニューが開かないようにするには、プロパティをに設定します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [ToolStrip コントロール](toolstrip-control-windows-forms.md)
