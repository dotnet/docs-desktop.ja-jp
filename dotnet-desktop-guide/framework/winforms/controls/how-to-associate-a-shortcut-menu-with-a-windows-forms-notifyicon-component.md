---
title: ショートカットメニューを NotifyIcon コンポーネントに関連付ける
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980963"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>方法: ショートカット メニューを Windows フォーム NotifyIcon コンポーネントに関連付ける
> [!NOTE]
> とは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 以前のバージョンのとのコントロールに置き換えて機能を追加しますが、を <xref:System.Windows.Forms.MainMenu> 選択した場合は、 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 下位互換性と将来の使用の両方で保持されます。  
  
 コンポーネントは、 <xref:System.Windows.Forms.NotifyIcon> タスクバーの状態通知領域にアイコンを表示します。 一般的に、アプリケーションでは、このアイコンを右クリックして、表示されるアプリケーションにコマンドを送信することができます。 コンポーネントをコンポーネントに関連付けることによって <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.NotifyIcon> 、この機能をアプリケーションに追加できます。  
  
> [!NOTE]
> タスクバーにコンポーネントのインスタンスを表示しているときに、起動時にアプリケーションを最小化する場合は <xref:System.Windows.Forms.NotifyIcon> 、メインフォームの <xref:System.Windows.Forms.Form.WindowState%2A> プロパティをに設定 <xref:System.Windows.Forms.FormWindowState.Minimized> し、 <xref:System.Windows.Forms.NotifyIcon> コンポーネントの <xref:System.Windows.Forms.NotifyIcon.Visible%2A> プロパティがに設定されていることを確認し `true` ます。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>デザイン時にショートカットメニューを NotifyIcon コンポーネントに関連付けるには  
  
1. コンポーネントを <xref:System.Windows.Forms.NotifyIcon> フォームに追加し、プロパティやプロパティなどの重要なプロパティを設定し <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> ます。  
  
     詳細については、「 [方法: Windows フォーム NotifyIcon コンポーネントを使用してアプリケーションアイコンをタスクバーに追加する](app-icons-to-the-taskbar-with-wf-notifyicon.md)」を参照してください。  
  
2. コンポーネントを <xref:System.Windows.Forms.ContextMenu> Windows フォームに追加します。  
  
     実行時に使用できるようにするコマンドを表すメニュー項目をショートカットメニューに追加します。 これは、アクセスキーなどのメニュー項目にメニューの機能強化を追加する場合にも適しています。  
  
3. <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>コンポーネントのプロパティを、 <xref:System.Windows.Forms.NotifyIcon> 追加したショートカットメニューに設定します。  
  
     このプロパティを設定すると、タスクバーのアイコンがクリックされたときにショートカットメニューが表示されます。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>プログラムによってショートカットメニューを NotifyIcon コンポーネントに関連付けるには  
  
1. クラスのインスタンス <xref:System.Windows.Forms.NotifyIcon> とクラスを作成し <xref:System.Windows.Forms.ContextMenu> ます。このとき、アプリケーションに必要なプロパティ設定 ( <xref:System.Windows.Forms.NotifyIcon.Icon%2A> および <xref:System.Windows.Forms.NotifyIcon.Visible%2A> コンポーネントのメニュー項目のプロパティ) を使用し <xref:System.Windows.Forms.NotifyIcon> <xref:System.Windows.Forms.ContextMenu> ます。  
  
2. <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>コンポーネントのプロパティを、 <xref:System.Windows.Forms.NotifyIcon> 追加したショートカットメニューに設定します。  
  
     このプロパティを設定すると、タスクバーのアイコンがクリックされたときにショートカットメニューが表示されます。  
  
    > [!NOTE]
    > 次のコード例では、基本的なメニュー構造を作成します。 メニューの選択肢は、開発中のアプリケーションに適したものにカスタマイズする必要があります。 また、 <xref:System.Windows.Forms.MenuItem.Click> これらのメニュー項目のイベントを処理するコードを記述することもできます。  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _
          (System.Environment.GetFolderPath _
          (System.Environment.SpecialFolder.Personal)  _
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> を初期化する必要があります `notifyIcon1` `contextMenu1,` 。これを行うには、フォームのコンストラクターに次のステートメントを追加します。  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [方法: Windows フォームの NotifyIcon コンポーネントによってタスクバーにアプリケーション アイコンを追加する](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon コンポーネント](notifyicon-component-windows-forms.md)
- [NotifyIcon コンポーネントの概要](notifyicon-component-overview-windows-forms.md)
