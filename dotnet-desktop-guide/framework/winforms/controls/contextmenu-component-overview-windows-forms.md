---
title: ContextMenu コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974282"
---
# <a name="contextmenu-component-overview-windows-forms"></a>ContextMenu コンポーネントの概要 (Windows フォーム)
> [!IMPORTANT]
> とは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 以前のバージョンのとのコントロールに置き換えて機能を追加しますが、を <xref:System.Windows.Forms.MainMenu> 選択した場合は、 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 下位互換性と将来の使用の両方で保持されます。  
  
 Windows フォームコンポーネントを使用 <xref:System.Windows.Forms.ContextMenu> すると、選択したオブジェクトに関連付けられている頻繁に使用するコマンドのショートカットメニューをユーザーに提供できます。 ショートカットメニューの項目は、多くの場合、アプリケーションの他の場所に表示されるメインメニューの項目のサブセットです。 ユーザーは、通常、マウスを右クリックしてショートカットメニューにアクセスできます。 Windows フォームでは、ショートカットメニューはコントロールに関連付けられています。  
  
## <a name="key-properties"></a>キー プロパティ  
 コントロールのプロパティをコンポーネントに設定することによって、ショートカットメニューをコントロールに関連付けることができ <xref:System.Windows.Forms.Control.ContextMenu%2A> <xref:System.Windows.Forms.ContextMenu> ます。 1つのショートカットメニューを複数のコントロールに関連付けることができますが、各コントロールにはショートカットメニューを1つしか含めることができません。  
  
 コンポーネントのキープロパティ <xref:System.Windows.Forms.ContextMenu> は、 <xref:System.Windows.Forms.Menu.MenuItems%2A> プロパティです。 プログラムによって <xref:System.Windows.Forms.MenuItem> オブジェクトを作成し、ショートカットメニューのに追加することによって、メニュー項目を追加でき <xref:System.Windows.Forms.Menu.MenuItemCollection> ます。 ショートカットメニュー内の項目は通常、他のメニューから描画されるので、ほとんどの場合、項目をコピーすることでショートカットメニューに追加します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
