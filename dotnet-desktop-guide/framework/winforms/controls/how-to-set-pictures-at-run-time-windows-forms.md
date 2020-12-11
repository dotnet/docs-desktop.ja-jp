---
title: '方法: 実行時にピクチャを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: 5cbbfa69f049ef410398c999eb6e9eca3cc9be3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980278"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>方法 : 実行時にピクチャを設定する (Windows フォーム)

Windows フォームコントロールによって表示されるイメージをプログラムで設定でき <xref:System.Windows.Forms.PictureBox> ます。  
  
### <a name="to-set-a-picture-programmatically"></a>プログラムによって画像を設定するには  
  
- <xref:System.Windows.Forms.PictureBox.Image%2A>クラスのメソッドを使用して、プロパティを設定し <xref:System.Drawing.Image.FromFile%2A> <xref:System.Drawing.Image> ます。  
  
     次の例では、イメージの場所に設定されたパスが [マイドキュメント] フォルダーです。 これは、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのディレクトリが含まれると想定できるためです。 また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。 次の例では、フォームに <xref:System.Windows.Forms.PictureBox> コントロールが既に追加されていることを前提としています。  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>グラフィックをクリアするには  
  
- まず、イメージによって使用されているメモリを解放し、グラフィックをクリアします。 ガベージコレクションでは、メモリ管理が問題になると、メモリが解放されます。  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > この方法でメソッドを使用する理由の詳細につい <xref:System.Drawing.Image.Dispose%2A> ては、「 [アンマネージリソースのクリーンアップ](/dotnet/standard/garbage-collection/unmanage)」を参照してください。  
  
     このコードは、デザイン時にグラフィックがコントロールに読み込まれた場合でも、イメージをクリアします。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [PictureBox コントロールの概要](picturebox-control-overview-windows-forms.md)
- [方法: デザイナーを使用してピクチャを読み込む](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [方法: 実行時にピクチャのサイズまたは配置を変更する](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox コントロール](picturebox-control-windows-forms.md)
