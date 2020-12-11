---
title: '方法: ツール バー ボタンのアイコンを定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 84c67c7d2584390ba3e48cb83820c65c6bb45d1f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982156"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a>方法: ツール バー ボタンのアイコンを定義する
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。  
  
 <xref:System.Windows.Forms.ToolBar> ボタンは、ユーザーが簡単に識別できるように、それらの中にアイコンを表示できます。 これは、 [ImageList コンポーネント](imagelist-component-windows-forms.md) コンポーネントにイメージを追加し、コンポーネントをコントロールに関連付けることによって実現され <xref:System.Windows.Forms.ImageList> <xref:System.Windows.Forms.ToolBar> ます。  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a>プログラムによってツールバーボタンのアイコンを設定するには  
  
1. プロシージャでは、コンポーネントとコントロールをインスタンス化し <xref:System.Windows.Forms.ImageList> <xref:System.Windows.Forms.ToolBar> ます。  
  
2. 同じ手順で、コンポーネントにイメージを割り当て <xref:System.Windows.Forms.ImageList> ます。  
  
3. 同じ手順で、コントロール <xref:System.Windows.Forms.ImageList> をコントロールに割り当て、 <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 個々のツールバーボタンのプロパティを割り当てます。  
  
     次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント** ] フォルダーです。 これは、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのディレクトリが含まれると想定できるためです。 また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。 次の例では、フォームに <xref:System.Windows.Forms.PictureBox> コントロールが既に追加されていることを前提としています。  
  
     上記の手順に従うと、次のようなコードを記述する必要があります。  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolBar>
- [方法: ツール バー ボタンのメニュー イベントをトリガーする](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar コントロール](toolbar-control-windows-forms.md)
- [ImageList コンポーネント](imagelist-component-windows-forms.md)
