---
title: StatusBar コントロールでクリックされたパネルを確認する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974178"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>方法: Windows フォームの StatusBar コントロールでクリックされたパネルを確認する
> [!IMPORTANT]
> コントロールとコントロールは、およびコントロール <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> に対して、機能の置き換えと追加を行います。ただし、コントロール <xref:System.Windows.Forms.StatusBar> とコントロールは、 <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 下位互換性と将来の使用の両方について、選択した場合に保持されます。  
  
 ユーザーのクリックに応答するように [StatusBar コントロール](statusbar-control-windows-forms.md) コントロールをプログラミングするには、イベント内で case ステートメントを使用し <xref:System.Windows.Forms.StatusBar.PanelClick> ます。 イベントには、クリックされたへの参照を含む引数 (パネル引数) が含まれてい <xref:System.Windows.Forms.StatusBarPanel> ます。 この参照を使用して、クリックされたパネルのインデックスを特定し、それに応じてプログラムを作成できます。  
  
> [!NOTE]
> <xref:System.Windows.Forms.StatusBar>コントロールの <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> プロパティがに設定されていることを確認し `true` ます。  
  
### <a name="to-determine-which-panel-was-clicked"></a>クリックされたパネルを確認するには  
  
1. イベントハンドラーでは、 <xref:System.Windows.Forms.StatusBar.PanelClick> `Select Case` (Visual Basic) または `switch case` (Visual C# または Visual C++) のステートメントを使用して、クリックされたパネルを判別します。これを行うには、イベント引数でクリックしたパネルのインデックスを調べます。  
  
     次のコード例では、 <xref:System.Windows.Forms.StatusBar> コントロール、 `StatusBar1` 、およびという2つのオブジェクトのプレゼンスをフォームに指定する必要があり <xref:System.Windows.Forms.StatusBarPanel> `StatusBarPanel1` `StatusBarPanel2` ます。  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     (Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [方法: ステータス バー パネルのサイズを設定する](how-to-set-the-size-of-status-bar-panels.md)
- [チュートリアル: ステータス バー情報の実行時更新](walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar コントロールの概要](statusbar-control-overview-windows-forms.md)
