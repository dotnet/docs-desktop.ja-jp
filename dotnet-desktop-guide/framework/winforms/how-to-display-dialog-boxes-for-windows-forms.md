---
title: '方法: ダイアログボックスを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974345"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>方法: Windows フォームのダイアログ ボックスを表示する
アプリケーションで他のフォームを表示する場合と同じ方法でダイアログボックスを表示します。 スタートアップフォームは、アプリケーションの実行時に自動的に読み込まれます。 アプリケーションに2つ目のフォームまたはダイアログボックスが表示されるようにするには、それを読み込んで表示するためのコードを記述します。 同様に、フォームまたはダイアログボックスが表示されないようにするには、アンロードまたは非表示にするコードを記述します。  
  
### <a name="to-display-a-dialog-box"></a>ダイアログボックスを表示するには  
  
1. ダイアログボックスを開くイベントハンドラーに移動します。 これは、メニューコマンドが選択されている場合、ボタンがクリックされた場合、または他のイベントが発生した場合に発生する可能性があります。  
  
2. イベントハンドラーで、ダイアログボックスを開くためのコードを追加します。 この例では、ボタンクリックイベントを使用してダイアログボックスを表示しています。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
