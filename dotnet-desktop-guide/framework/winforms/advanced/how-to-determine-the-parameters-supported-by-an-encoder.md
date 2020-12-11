---
title: '方法: エンコーダーがサポートするパラメーターの確認'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 3e5345180e0ff3321b9ef0b885b836d3e9456f28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974407"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="d5c76-102">方法: エンコーダーがサポートするパラメーターの確認</span><span class="sxs-lookup"><span data-stu-id="d5c76-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="d5c76-103">画質や圧縮レベルなどのイメージパラメーターを調整できますが、特定のイメージエンコーダーでサポートされているパラメーターを把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5c76-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="d5c76-104">クラスは、 <xref:System.Drawing.Image> <xref:System.Drawing.Image.GetEncoderParameterList%2A> 特定のエンコーダーでサポートされているイメージパラメーターを判別できるように、メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5c76-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="d5c76-105">エンコーダーには GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c76-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="d5c76-106">メソッドは、 <xref:System.Drawing.Image.GetEncoderParameterList%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.EncoderParameter> ます。</span><span class="sxs-lookup"><span data-stu-id="d5c76-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c76-107">例</span><span class="sxs-lookup"><span data-stu-id="d5c76-107">Example</span></span>  
 <span data-ttu-id="d5c76-108">次のコード例では、JPEG エンコーダーでサポートされているパラメーターを出力します。</span><span class="sxs-lookup"><span data-stu-id="d5c76-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="d5c76-109">クラスの概要でパラメーターカテゴリと関連付けられている Guid の一覧を使用して、 <xref:System.Drawing.Imaging.Encoder> 各パラメーターのカテゴリを決定します。</span><span class="sxs-lookup"><span data-stu-id="d5c76-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5c76-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d5c76-110">Compiling the Code</span></span>  
 <span data-ttu-id="d5c76-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5c76-111">This example requires:</span></span>  
  
- <span data-ttu-id="d5c76-112">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d5c76-112">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="d5c76-113"><xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="d5c76-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c76-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5c76-114">See also</span></span>

- [<span data-ttu-id="d5c76-115">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="d5c76-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="d5c76-116">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="d5c76-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="d5c76-117">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="d5c76-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
