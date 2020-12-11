---
title: ContextMenu コンポーネントを使用したメニュー項目の追加と削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981123"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>方法: Windows フォーム ContextMenu コンポーネントのメニュー項目を追加および削除する
Windows フォームでショートカットメニュー項目を追加および削除する方法について説明します。  
  
 Windows フォームコンポーネントには、 <xref:System.Windows.Forms.ContextMenu> 選択したオブジェクトに関連する頻繁に使用するコマンドのメニューが用意されています。 オブジェクトをコレクションに追加することで、ショートカットメニューに項目を追加でき <xref:System.Windows.Forms.MenuItem> <xref:System.Windows.Forms.Menu.MenuItems%2A> ます。  
  
 ショートカットメニューから項目を完全に削除することができます。ただし、実行時には、代わりに項目を非表示にしたり無効にしたりする方が適切な場合があります。  
  
> [!IMPORTANT]
> とは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 以前のバージョンのとのコントロールに置き換えて機能を追加しますが、を <xref:System.Windows.Forms.MainMenu> 選択した場合は、 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 下位互換性と将来の使用の両方で保持されます。  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>ショートカットメニューから項目を削除するには  
  
1. 特定の <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.Menu.MenuItems%2A> <xref:System.Windows.Forms.ContextMenu> メニュー項目を削除するには、コンポーネントのコレクションのメソッドまたはメソッドを使用します。  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     または  
  
2. `Clear`コンポーネントのコレクションのメソッドを使用して、 `MenuItems` <xref:System.Windows.Forms.ContextMenu> メニューからすべての項目を削除します。  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ContextMenu>
- [ContextMenu コンポーネント](contextmenu-component-windows-forms.md)
- [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)
