---
title: '方法: ToolStripMenuItems に拡張機能を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982267"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>方法: ToolStripMenuItems に拡張機能を追加する
次の方法で、およびコントロールの使いやすさを向上させることができ <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> ます。  
  
- チェックマークを追加して、機能を有効にするかどうかを指定します。たとえば、ワードプロセッシングアプリケーションの余白に沿ってルーラーを表示するかどうか、ファイルの一覧に表示されるファイル ([ **ウィンドウ** ] メニューなど) を指定します。  
  
- メニューコマンドを視覚的に表すイメージを追加します。  
  
- ショートカットキーを表示して、コマンドを実行するためのキーボード代替手段をマウスに提供します。 たとえば、CTRL キーを押しながら C キーを押すと、 **Copy** コマンドが実行されます。  
  
- アクセスキーを表示して、メニューナビゲーション用のマウスの代わりにキーボードを使用できるようにします。 たとえば、ALT キーを押しながら F キーを押すと、[ **ファイル** ] メニューが選択されます。  
  
- 区分線を表示して関連するコマンドをグループ化し、メニューを読みやすくします。  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>メニューコマンドにチェックマークを表示するには  
  
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>プロパティをに設定 `true` します。  
  
     これにより、プロパティもに設定され <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> `true` ます。 この手順は、メニューコマンドが選択されているかどうかに関係なく、既定でオンになっている場合にのみ使用してください。  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>各クリックで状態を変更するチェックマークを表示するには  
  
- メニューコマンドの <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> プロパティをに設定 `true` します。  
  
### <a name="to-add-an-image-to-a-menu-command"></a>メニューコマンドにイメージを追加するには  
  
- メニューコマンドの <xref:System.Windows.Forms.ToolStripItem.Image%2A> プロパティをイメージの名前に設定します。 <xref:System.Windows.Forms.ToolStripItemDisplayStyle>このメニューコマンドのプロパティがまたはに設定されている場合は、 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> イメージを表示できません。  
  
> [!NOTE]
> 画像の余白では、選択した場合にチェックマークを表示することもできます。 また、 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> イメージのプロパティをに設定すると、 `true` 実行時にイメージがハッチ境界線で囲まれて表示されます。  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>メニューコマンドのショートカットキーを表示するには  
  
- メニューコマンドのプロパティを、[ <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> メニューを **開く** ] コマンドの CTRL + O などの目的のキーボードの組み合わせに設定し、 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> プロパティをに設定し `true` ます。  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>メニューコマンドのカスタムショートカットキーを表示するには  
  
- メニューコマンドのプロパティに、 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> shift + CTRL + o ではなく、ctrl + shift + o などの目的のキーボードの組み合わせを設定し、 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> プロパティをに設定し `true` ます。  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>メニューコマンドのアクセスキーを表示するには  
  
- メニューコマンドのプロパティを設定するときに <xref:System.Windows.Forms.ToolStripItem.Text%2A> 、アクセスキーとして下線を付ける文字の前にアンパサンド (&) を入力します。 たとえば、 `&Open` メニュー項目のプロパティとして「」と入力すると、 <xref:System.Windows.Forms.ToolStripItem.Text%2A> メニューコマンドが <u>O</u>ペンとして表示されます。
  
     このメニューコマンドに移動するには、ALT キーを押してにフォーカスを移し、 <xref:System.Windows.Forms.MenuStrip> メニュー名のアクセスキーを押します。 メニューが開き、アクセスキーを持つ項目が表示されたら、アクセスキーを押してメニューコマンドを選択するだけです。  
  
> [!NOTE]
> 同じメニューシステムで ALT + F を2回定義するなど、重複するアクセスキーを定義することは避けてください。 重複するアクセスキーの選択順序を保証することはできません。  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>メニューコマンドの間に区切りバーを表示するには  
  
- とそれに含まれる項目を定義したら、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> メソッドまたはメソッドを使用して <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 、メニューコマンドと <xref:System.Windows.Forms.ToolStripSeparator> コントロールを目的の順序でに追加し <xref:System.Windows.Forms.MenuStrip> ます。  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,
    ' and the Save and Exit menu commands to the top-level File menu,
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,
    // and the Save and Exit menu commands to the top-level File menu,
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip コントロールの概要](menustrip-control-overview-windows-forms.md)
