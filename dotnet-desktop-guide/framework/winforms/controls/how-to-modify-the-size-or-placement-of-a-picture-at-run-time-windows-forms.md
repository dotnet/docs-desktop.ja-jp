---
title: '方法: 実行時にピクチャのサイズまたは配置を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980756"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>方法 : 実行時にピクチャのサイズまたは配置を変更する (Windows フォーム)
フォームで Windows フォームコントロールを使用する場合は、 <xref:System.Windows.Forms.PictureBox> プロパティを次の <xref:System.Windows.Forms.PictureBox.SizeMode%2A> ように設定できます。  
  
- 画像の左上隅をコントロールの左上隅に揃えます  
  
- コントロール内の画像を中央に配置する  
  
- 表示する画像に合わせてコントロールのサイズを調整する  
  
- コントロールに合わせるために表示される画像を拡大する  
  
 画像 (特にビットマップ形式) を拡大すると、画質が低下する可能性があります。 実行時にイメージを描画するためのグラフィックス命令の一覧であるメタファイルは、ビットマップの場合よりも伸縮に適しています。  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>実行時に SizeMode プロパティを設定するには  
  
1. を <xref:System.Windows.Forms.PictureBox.SizeMode%2A> <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (既定値)、、 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 、またはに設定し <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> ます。 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> は、イメージがコントロールの左上隅に配置されることを意味します。イメージがコントロールよりも大きい場合は、下端と右端がクリップされます。 <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> は、イメージがコントロール内で中央に配置されることを意味します。画像がコントロールより大きい場合は、画像の外側がクリップされます。 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> は、コントロールのサイズがイメージのサイズに合わせて調整されることを意味します。 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> は逆順であり、はイメージのサイズがコントロールのサイズに合わせて調整されることを意味します。  
  
     次の例では、イメージの場所に設定されたパスが [マイドキュメント] フォルダーです。 これは、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのディレクトリが含まれると想定できるためです。 また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。 次の例では、フォームに <xref:System.Windows.Forms.PictureBox> コントロールが既に追加されていることを前提としています。  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PictureBox>
- [方法: デザイナーを使用してピクチャを読み込む](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [PictureBox コントロールの概要](picturebox-control-overview-windows-forms.md)
- [方法: 実行時にピクチャを設定する](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox コントロール](picturebox-control-windows-forms.md)
