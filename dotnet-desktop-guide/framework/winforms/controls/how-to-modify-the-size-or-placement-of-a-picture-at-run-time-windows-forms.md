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
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="0bd60-102">方法 : 実行時にピクチャのサイズまたは配置を変更する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="0bd60-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="0bd60-103">フォームで Windows フォームコントロールを使用する場合は、 <xref:System.Windows.Forms.PictureBox> プロパティを次の <xref:System.Windows.Forms.PictureBox.SizeMode%2A> ように設定できます。</span><span class="sxs-lookup"><span data-stu-id="0bd60-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="0bd60-104">画像の左上隅をコントロールの左上隅に揃えます</span><span class="sxs-lookup"><span data-stu-id="0bd60-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="0bd60-105">コントロール内の画像を中央に配置する</span><span class="sxs-lookup"><span data-stu-id="0bd60-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="0bd60-106">表示する画像に合わせてコントロールのサイズを調整する</span><span class="sxs-lookup"><span data-stu-id="0bd60-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="0bd60-107">コントロールに合わせるために表示される画像を拡大する</span><span class="sxs-lookup"><span data-stu-id="0bd60-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="0bd60-108">画像 (特にビットマップ形式) を拡大すると、画質が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bd60-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="0bd60-109">実行時にイメージを描画するためのグラフィックス命令の一覧であるメタファイルは、ビットマップの場合よりも伸縮に適しています。</span><span class="sxs-lookup"><span data-stu-id="0bd60-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="0bd60-110">実行時に SizeMode プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="0bd60-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="0bd60-111">を <xref:System.Windows.Forms.PictureBox.SizeMode%2A> <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (既定値)、、 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 、またはに設定し <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> ます。</span><span class="sxs-lookup"><span data-stu-id="0bd60-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="0bd60-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> は、イメージがコントロールの左上隅に配置されることを意味します。イメージがコントロールよりも大きい場合は、下端と右端がクリップされます。</span><span class="sxs-lookup"><span data-stu-id="0bd60-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="0bd60-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> は、イメージがコントロール内で中央に配置されることを意味します。画像がコントロールより大きい場合は、画像の外側がクリップされます。</span><span class="sxs-lookup"><span data-stu-id="0bd60-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="0bd60-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> は、コントロールのサイズがイメージのサイズに合わせて調整されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0bd60-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="0bd60-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> は逆順であり、はイメージのサイズがコントロールのサイズに合わせて調整されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0bd60-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="0bd60-116">次の例では、イメージの場所に設定されたパスが [マイドキュメント] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0bd60-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="0bd60-117">これは、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのディレクトリが含まれると想定できるためです。</span><span class="sxs-lookup"><span data-stu-id="0bd60-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="0bd60-118">また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0bd60-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="0bd60-119">次の例では、フォームに <xref:System.Windows.Forms.PictureBox> コントロールが既に追加されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0bd60-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0bd60-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bd60-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="0bd60-121">方法: デザイナーを使用してピクチャを読み込む</span><span class="sxs-lookup"><span data-stu-id="0bd60-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="0bd60-122">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0bd60-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="0bd60-123">方法: 実行時にピクチャを設定する</span><span class="sxs-lookup"><span data-stu-id="0bd60-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="0bd60-124">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="0bd60-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
