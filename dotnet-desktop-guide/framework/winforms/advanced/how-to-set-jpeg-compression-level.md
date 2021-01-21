---
title: '方法: JPEG 圧縮レベルの設定'
description: Windows フォームで圧縮レベルを変更して、JPEG イメージの品質を調整する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], changing encoder parameters
- JPEG images [Windows Forms], setting quality level
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
ms.openlocfilehash: 20c34bdec1b55a74f7ec005b3948ac123585155d
ms.sourcegitcommit: 302273bd74509dfbff11126753dd210d80f1bc37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536001"
---
# <a name="how-to-set-jpeg-compression-level"></a><span data-ttu-id="f1999-103">方法: JPEG 圧縮レベルの設定</span><span class="sxs-lookup"><span data-stu-id="f1999-103">How to: Set JPEG Compression Level</span></span>
<span data-ttu-id="f1999-104">イメージをディスクに保存するときに、ファイル サイズを最小化したり品質を向上させるために、イメージのパラメーターを修正したりする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1999-104">You may want to modify the parameters of an image when you save the image to disk to minimize the file size or improve its quality.</span></span> <span data-ttu-id="f1999-105">圧縮レベルを修正して、JPEG イメージの品質を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="f1999-105">You can adjust the quality of a JPEG image by modifying its compression level.</span></span> <span data-ttu-id="f1999-106">JPEG イメージを保存するときに圧縮レベルを指定するには、オブジェクトを作成 <xref:System.Drawing.Imaging.EncoderParameters> し、そのオブジェクトをクラスのメソッドに渡す必要があり <xref:System.Drawing.Image.Save%2A> <xref:System.Drawing.Image> ます。</span><span class="sxs-lookup"><span data-stu-id="f1999-106">To specify the compression level when you save a JPEG image, you must create an <xref:System.Drawing.Imaging.EncoderParameters> object and pass it to the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="f1999-107">オブジェクトを初期化して、 <xref:System.Drawing.Imaging.EncoderParameters> 1 つの配列が含まれるようにし <xref:System.Drawing.Imaging.EncoderParameter> ます。</span><span class="sxs-lookup"><span data-stu-id="f1999-107">Initialize the <xref:System.Drawing.Imaging.EncoderParameters> object so that it has an array that consists of one <xref:System.Drawing.Imaging.EncoderParameter>.</span></span> <span data-ttu-id="f1999-108">を作成するときに <xref:System.Drawing.Imaging.EncoderParameter> 、 <xref:System.Drawing.Imaging.Encoder.Quality> エンコーダーと必要な圧縮レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1999-108">When you create the <xref:System.Drawing.Imaging.EncoderParameter>, specify the <xref:System.Drawing.Imaging.Encoder.Quality> encoder, and the desired compression level.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1999-109">例</span><span class="sxs-lookup"><span data-stu-id="f1999-109">Example</span></span>  
 <span data-ttu-id="f1999-110">次のコード例では、 <xref:System.Drawing.Imaging.EncoderParameter> オブジェクトを作成し、3つの JPEG イメージを保存します。</span><span class="sxs-lookup"><span data-stu-id="f1999-110">The following example code creates an <xref:System.Drawing.Imaging.EncoderParameter> object and saves three JPEG images.</span></span> <span data-ttu-id="f1999-111">各 JPEG イメージは、 `long` コンストラクターに渡される値を変更することによって、異なる品質レベルで保存され <xref:System.Drawing.Imaging.EncoderParameter> ます。</span><span class="sxs-lookup"><span data-stu-id="f1999-111">Each JPEG image is saved with a different quality level, by modifying the `long` value passed to the <xref:System.Drawing.Imaging.EncoderParameter> constructor.</span></span> <span data-ttu-id="f1999-112">品質レベル 0 は最も圧縮率が高く、品質レベル 100 は最も低い圧縮率に対応します。</span><span class="sxs-lookup"><span data-stu-id="f1999-112">A quality level of 0 corresponds to the greatest compression, and a quality level of 100 corresponds to the least compression.</span></span>  
  
```csharp  
private void VaryQualityLevel()  
    {  
        // Get a bitmap. The using statement ensures objects  
        // are automatically disposed from memory after use.  
        using (Bitmap bmp1 = new Bitmap(@"C:\TestPhoto.jpg"))  
        {  
            ImageCodecInfo jpgEncoder = GetEncoder(ImageFormat.Jpeg);  
  
            // Create an Encoder object based on the GUID  
            // for the Quality parameter category.  
            System.Drawing.Imaging.Encoder myEncoder =  
                System.Drawing.Imaging.Encoder.Quality;  
  
            // Create an EncoderParameters object.  
            // An EncoderParameters object has an array of EncoderParameter  
            // objects. In this case, there is only one  
            // EncoderParameter object in the array.  
            EncoderParameters myEncoderParameters = new EncoderParameters(1);  
  
            EncoderParameter myEncoderParameter = new EncoderParameter(myEncoder, 50L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"c:\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters);  
  
            myEncoderParameter = new EncoderParameter(myEncoder, 100L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters);  
  
            // Save the bitmap as a JPG file with zero quality level compression.  
            myEncoderParameter = new EncoderParameter(myEncoder, 0L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters);  
        }  
    }  
```  
  
```vb  
Private Sub VaryQualityLevel()  
    ' Get a bitmap. The Using statement ensures objects  
    ' are automatically disposed from memory after use.  
    Using bmp1 As New Bitmap("C:\test\TestPhoto.jpg")  
        Dim jpgEncoder As ImageCodecInfo = GetEncoder(ImageFormat.Jpeg)  
  
        ' Create an Encoder object based on the GUID  
        ' for the Quality parameter category.  
        Dim myEncoder As System.Drawing.Imaging.Encoder = System.Drawing.Imaging.Encoder.Quality  
  
        ' Create an EncoderParameters object.  
        ' An EncoderParameters object has an array of EncoderParameter  
        ' objects. In this case, there is only one  
        ' EncoderParameter object in the array.  
        Dim myEncoderParameters As New EncoderParameters(1)  
  
        Dim myEncoderParameter As New EncoderParameter(myEncoder, 50L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("c:\test\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters)  
  
        myEncoderParameter = New EncoderParameter(myEncoder, 100L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters)  
  
        ' Save the bitmap as a JPG file with zero quality level compression.  
        myEncoderParameter = New EncoderParameter(myEncoder, 0L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters)  
    End Using  
End Sub  
```  
  
```csharp  
private ImageCodecInfo GetEncoder(ImageFormat format)  
{  
    ImageCodecInfo[] codecs = ImageCodecInfo.GetImageEncoders();  
    foreach (ImageCodecInfo codec in codecs)  
    {  
        if (codec.FormatID == format.Guid)  
        {  
            return codec;  
        }  
    }  
    return null;  
}  
```  
  
```vb  
Private Function GetEncoder(ByVal format As ImageFormat) As ImageCodecInfo  
  
    Dim codecs As ImageCodecInfo() = ImageCodecInfo.GetImageEncoders()  
    Dim codec As ImageCodecInfo  
    For Each codec In codecs  
        If codec.FormatID = format.Guid Then  
            Return codec  
        End If  
    Next codec  
    Return Nothing  
  
End Function  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1999-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f1999-113">Compiling the Code</span></span>  
 <span data-ttu-id="f1999-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1999-114">This example requires:</span></span>  
  
- <span data-ttu-id="f1999-115">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f1999-115">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="f1999-116"><xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="f1999-116">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
- <span data-ttu-id="f1999-117">`TestPhoto.jpg` という名前のイメージ ファイル。保存場所は **c:\\** です。</span><span class="sxs-lookup"><span data-stu-id="f1999-117">An image file that is named `TestPhoto.jpg` and located at **c:\\**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1999-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1999-118">See also</span></span>

- [<span data-ttu-id="f1999-119">方法: エンコーダーがサポートするパラメーターの確認</span><span class="sxs-lookup"><span data-stu-id="f1999-119">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)
- [<span data-ttu-id="f1999-120">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="f1999-120">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="f1999-121">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="f1999-121">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
