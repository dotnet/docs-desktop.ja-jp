---
title: '方法: メニュー項目を ContextMenuStrip に追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 7e3480c5a56170ce94d5b5bde0208542c82e7702
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982015"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a>方法: メニュー項目を ContextMenuStrip に追加する
一度に1つのメニュー項目または複数の項目をに追加でき <xref:System.Windows.Forms.ContextMenuStrip> ます。  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a>単一のメニュー項目を ContextMenuStrip に追加するには  
  
- <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>に1つのメニュー項目を追加するには、メソッドを使用し <xref:System.Windows.Forms.ContextMenuStrip> ます。  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a>複数のメニュー項目を ContextMenuStrip に追加するには  
  
- <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>に複数のメニュー項目を追加するには、メソッドを使用し <xref:System.Windows.Forms.ContextMenuStrip> ます。  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a>関連項目

- [ContextMenuStrip コントロール](contextmenustrip-control.md)
