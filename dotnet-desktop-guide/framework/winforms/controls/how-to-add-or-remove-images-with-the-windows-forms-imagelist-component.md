---
title: ImageList コンポーネントを使用したイメージの追加または削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: e045be7ea9407bc379b0c22282fcd2184ff5db51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982016"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>方法: Windows フォームの ImageList コンポーネントにイメージを追加または削除する
Windows フォームコンポーネントには、 <xref:System.Windows.Forms.ImageList> 通常、コントロールに関連付けられる前にイメージが設定されます。 ただし、イメージリストをコントロールに関連付けた後に、イメージの追加や削除を行うことができます。  
  
> [!NOTE]
> イメージを削除する場合 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> は、関連付けられているコントロールのプロパティが有効であることを確認します。  
  
### <a name="to-add-images-programmatically"></a>プログラムによってイメージを追加するには  
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>イメージリストのプロパティのメソッドを使用し <xref:System.Windows.Forms.ImageList.Images%2A> ます。  
  
     次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント** ] フォルダーです。 この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。 また、この場所を選択すると、システムアクセスレベルを最小限にしたユーザーがアプリケーションをより安全に実行できるようになります。 次のコード例では、 <xref:System.Windows.Forms.ImageList> コントロールが既に追加されているフォームが必要です。  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a>キー値を使用してイメージを追加します。  
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>キー値を受け取るイメージリストのプロパティのメソッドのいずれかを使用し <xref:System.Windows.Forms.ImageList.Images%2A> ます。  
  
     次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント** ] フォルダーです。 この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。 また、この場所を選択すると、システムアクセスレベルを最小限にしたユーザーがアプリケーションをより安全に実行できるようになります。 次のコード例では、 <xref:System.Windows.Forms.ImageList> コントロールが既に追加されているフォームが必要です。  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a>プログラムによってすべてのイメージを削除するには  
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>1 つのイメージを削除するには、メソッドを使用します。  
  
     、-または-  
  
     <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>イメージリスト内のすべてのイメージをクリアするには、メソッドを使用します。  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a>キーによってイメージを削除するには  
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>キーによって1つのイメージを削除するには、メソッドを使用します。  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>関連項目

- [ImageList コンポーネント](imagelist-component-windows-forms.md)
- [ImageList コンポーネントの概要](imagelist-component-overview-windows-forms.md)
- [イメージ、ビットマップ、およびメタファイル](../advanced/images-bitmaps-and-metafiles.md)
