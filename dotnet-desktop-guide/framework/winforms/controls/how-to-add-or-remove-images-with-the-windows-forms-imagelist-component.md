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
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="377b6-102">方法: Windows フォームの ImageList コンポーネントにイメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="377b6-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="377b6-103">Windows フォームコンポーネントには、 <xref:System.Windows.Forms.ImageList> 通常、コントロールに関連付けられる前にイメージが設定されます。</span><span class="sxs-lookup"><span data-stu-id="377b6-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="377b6-104">ただし、イメージリストをコントロールに関連付けた後に、イメージの追加や削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="377b6-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="377b6-105">イメージを削除する場合 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> は、関連付けられているコントロールのプロパティが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="377b6-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="377b6-106">プログラムによってイメージを追加するには</span><span class="sxs-lookup"><span data-stu-id="377b6-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="377b6-107"><xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>イメージリストのプロパティのメソッドを使用し <xref:System.Windows.Forms.ImageList.Images%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="377b6-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="377b6-108">次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント** ] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="377b6-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="377b6-109">この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。</span><span class="sxs-lookup"><span data-stu-id="377b6-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="377b6-110">また、この場所を選択すると、システムアクセスレベルを最小限にしたユーザーがアプリケーションをより安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="377b6-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="377b6-111">次のコード例では、 <xref:System.Windows.Forms.ImageList> コントロールが既に追加されているフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="377b6-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="377b6-112">キー値を使用してイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="377b6-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="377b6-113"><xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>キー値を受け取るイメージリストのプロパティのメソッドのいずれかを使用し <xref:System.Windows.Forms.ImageList.Images%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="377b6-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="377b6-114">次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント** ] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="377b6-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="377b6-115">この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。</span><span class="sxs-lookup"><span data-stu-id="377b6-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="377b6-116">また、この場所を選択すると、システムアクセスレベルを最小限にしたユーザーがアプリケーションをより安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="377b6-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="377b6-117">次のコード例では、 <xref:System.Windows.Forms.ImageList> コントロールが既に追加されているフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="377b6-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="377b6-118">プログラムによってすべてのイメージを削除するには</span><span class="sxs-lookup"><span data-stu-id="377b6-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="377b6-119"><xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>1 つのイメージを削除するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="377b6-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="377b6-120">、-または-</span><span class="sxs-lookup"><span data-stu-id="377b6-120">,-or-</span></span>  
  
     <span data-ttu-id="377b6-121"><xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>イメージリスト内のすべてのイメージをクリアするには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="377b6-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="377b6-122">キーによってイメージを削除するには</span><span class="sxs-lookup"><span data-stu-id="377b6-122">To remove images by key</span></span>  
  
- <span data-ttu-id="377b6-123"><xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>キーによって1つのイメージを削除するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="377b6-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="377b6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="377b6-124">See also</span></span>

- [<span data-ttu-id="377b6-125">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="377b6-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="377b6-126">ImageList コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="377b6-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="377b6-127">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="377b6-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
