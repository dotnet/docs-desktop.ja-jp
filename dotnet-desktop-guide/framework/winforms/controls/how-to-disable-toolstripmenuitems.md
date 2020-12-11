---
title: '方法: ToolStripMenuItems を無効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982135"
---
# <a name="how-to-disable-toolstripmenuitems"></a>方法: ToolStripMenuItems を無効にする
ユーザーの操作に応じてメニュー項目を有効または無効にすることによって、ユーザーが実行できるコマンドを制限または拡大できます。 メニュー項目は、作成時に既定で有効になりますが、プロパティを使用して調整でき <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ます。 このプロパティは、デザイン時に [ **プロパティ** ] ウィンドウで操作することも、コードで設定することによってプログラムで操作することもできます。  
  
### <a name="to-disable-a-menu-item-programmatically"></a>プログラムによってメニュー項目を無効にするには  
  
- メニュー項目のプロパティを設定するメソッド内で、プロパティをに設定するコードを追加し <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false` ます。  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > メニューの1つ目または最上位レベルのメニュー項目を無効にすると、メニュー内に含まれるすべてのメニュー項目が非表示になりますが、無効にはなりません。 同様に、サブメニュー項目を含むメニュー項目を無効にしても、サブメニュー項目は非表示になりますが、無効にはなりません。 特定のメニューのすべてのコマンドをユーザーが使用できない場合は、そのメニュー全体を非表示にして無効にすることをお勧めします。これにより、クリーンなユーザーインターフェイスが提供されます。 メニューを非表示にして無効にし、メニューのすべての項目とサブメニュー項目を無効にする必要があります。非表示にしても、ショートカットキーを使用してメニューコマンドにアクセスすることはできないためです。 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>トップレベルメニュー項目のプロパティをに設定すると `false` 、メニュー全体が非表示になります。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [方法: ToolStripMenuItems を非表示にする](how-to-hide-toolstripmenuitems.md)
- [MenuStrip コントロールの概要](menustrip-control-overview-windows-forms.md)
