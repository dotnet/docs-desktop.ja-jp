---
title: マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981187"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="1ad38-102">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="1ad38-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="1ad38-103">名前空間には、 <xref:System.Drawing> <xref:System.Drawing.Image> イメージを <xref:System.Drawing.Bitmap> 格納および操作するためのクラスとクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1ad38-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="1ad38-104">GDI + でイメージエンコーダーを使用すると、イメージをメモリからディスクに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-104">By using image encoders in GDI+, you can write images from memory to disk.</span></span> <span data-ttu-id="1ad38-105">GDI + でイメージデコーダーを使用すると、ディスクからメモリにイメージを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-105">By using image decoders in GDI+, you can load images from disk into memory.</span></span> <span data-ttu-id="1ad38-106">エンコーダーは、オブジェクトまたはオブジェクト内のデータを、 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 指定されたディスクファイル形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="1ad38-107">デコーダーは、ディスクファイル内のデータを、オブジェクトおよびオブジェクトが必要とする形式に変換し <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="1ad38-108">GDI + には、次のファイルの種類をサポートするエンコーダーとデコーダーが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="1ad38-108">GDI+ has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="1ad38-109">BMP</span><span class="sxs-lookup"><span data-stu-id="1ad38-109">BMP</span></span>  
  
- <span data-ttu-id="1ad38-110">GIF</span><span class="sxs-lookup"><span data-stu-id="1ad38-110">GIF</span></span>  
  
- <span data-ttu-id="1ad38-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="1ad38-111">JPEG</span></span>  
  
- <span data-ttu-id="1ad38-112">PNG</span><span class="sxs-lookup"><span data-stu-id="1ad38-112">PNG</span></span>  
  
- <span data-ttu-id="1ad38-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="1ad38-113">TIFF</span></span>  
  
 <span data-ttu-id="1ad38-114">GDI + には、次のファイルの種類をサポートする組み込みのデコーダーもあります。</span><span class="sxs-lookup"><span data-stu-id="1ad38-114">GDI+ also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="1ad38-115">WMF</span><span class="sxs-lookup"><span data-stu-id="1ad38-115">WMF</span></span>  
  
- <span data-ttu-id="1ad38-116">EMF</span><span class="sxs-lookup"><span data-stu-id="1ad38-116">EMF</span></span>  
  
- <span data-ttu-id="1ad38-117">ICON</span><span class="sxs-lookup"><span data-stu-id="1ad38-117">ICON</span></span>  
  
 <span data-ttu-id="1ad38-118">次のトピックでは、エンコーダーとデコーダーについてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ad38-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ad38-119">In This Section</span></span>  
 [<span data-ttu-id="1ad38-120">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="1ad38-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="1ad38-121">コンピューターで使用可能なエンコーダーを一覧表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="1ad38-122">方法: インストールされたデコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="1ad38-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="1ad38-123">コンピューターで使用可能なデコーダーを一覧表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="1ad38-124">方法: エンコーダーがサポートするパラメーターの確認</span><span class="sxs-lookup"><span data-stu-id="1ad38-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="1ad38-125">エンコーダーによってサポートされるの一覧を表示する方法について説明し <xref:System.Drawing.Imaging.EncoderParameters> ます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="1ad38-126">方法: BMP イメージから PNG イメージへの変換</span><span class="sxs-lookup"><span data-stu-id="1ad38-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="1ad38-127">イメージを別のイメージ形式で保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="1ad38-128">方法: JPEG 圧縮レベルの設定</span><span class="sxs-lookup"><span data-stu-id="1ad38-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="1ad38-129">イメージの品質レベルを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1ad38-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ad38-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="1ad38-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ad38-131">Related Sections</span></span>  
 [<span data-ttu-id="1ad38-132">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="1ad38-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="1ad38-133">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="1ad38-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
