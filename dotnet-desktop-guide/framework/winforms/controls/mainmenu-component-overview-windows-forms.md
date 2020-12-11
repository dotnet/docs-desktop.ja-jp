---
title: MainMenu コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980624"
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu コンポーネントの概要 (Windows フォーム)
> [!IMPORTANT]
> とは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 以前のバージョンのとのコントロールに置き換えて機能を追加しますが、を <xref:System.Windows.Forms.MainMenu> 選択した場合は、 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 下位互換性と将来の使用の両方で保持されます。  
  
 Windows フォームコンポーネントは、 <xref:System.Windows.Forms.MainMenu> 実行時にメニューを表示します。 メインメニューのすべてのサブメニューと個々の項目は <xref:System.Windows.Forms.MenuItem> オブジェクトです。  
  
## <a name="key-properties"></a>キー プロパティ  
 メニュー項目は、プロパティをに設定することによって、既定の項目として指定でき <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> `true` ます。 メニューがクリックされると、既定の項目が太字で表示されます。 メニュー項目の <xref:System.Windows.Forms.MenuItem.Checked%2A> プロパティは、またはのいずれかで、 `true` `false` メニュー項目が選択されているかどうかを示します。 メニュー項目のプロパティは、 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 選択した項目の外観をカスタマイズします。がに設定されている場合 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> `true` 、項目の横にオプションボタンが表示されます。がに設定されている場合は、 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> `false` 項目の横にチェックマークが表示されます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [MenuStrip コントロールの概要](menustrip-control-overview-windows-forms.md)
