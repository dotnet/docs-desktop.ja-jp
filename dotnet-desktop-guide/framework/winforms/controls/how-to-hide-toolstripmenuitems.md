---
title: '方法: ToolStripMenuItems を非表示にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 64c0f093063357c1e8db5933c035cc8295ad4f1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982104"
---
# <a name="how-to-hide-toolstripmenuitems"></a>方法: ToolStripMenuItems を非表示にする
メニュー項目を非表示にすることは、アプリケーションのユーザーインターフェイスを制御し、ユーザーコマンドを制限する方法です。 多くの場合、メニュー項目がすべて使用できなくなると、メニュー全体を非表示にすることができます。 これにより、ユーザーの取られるが減少します。 さらに、メニューまたはメニュー項目を非表示にしたり無効にしたりすることもできます。非表示にしても、ユーザーがショートカットキーを使用してメニューコマンドにアクセスするのを防ぐことはできません。  
  
### <a name="to-hide-any-menu-item-programmatically"></a>プログラムによってメニュー項目を非表示にするには  
  
- メニュー項目のプロパティを設定するメソッド内で、プロパティをに設定するコードを追加し <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false` ます。  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip コントロールの概要](menustrip-control-overview-windows-forms.md)
- [方法: ToolStripMenuItems を無効にする](how-to-disable-toolstripmenuitems.md)
