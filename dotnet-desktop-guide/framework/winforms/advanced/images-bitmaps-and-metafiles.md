---
title: イメージ、ビットマップ、およびメタファイル
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
ms.openlocfilehash: 5f50d21f4793efb497eb5b030d96a7dc3ab54a04
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981708"
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="1dc7d-102">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="1dc7d-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="1dc7d-103">`Image` クラスはラスター イメージ (ビットマップ) およびベクター イメージ (メタファイル) を操作するためのメソッドを提供する抽象基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="1dc7d-104">`Bitmap` クラスおよび <xref:System.Drawing.Imaging.Metafile> クラスは、どちらも `Image` クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="1dc7d-105">`Bitmap` クラスは、ラスター イメージの読み込み、保存、および操作のための追加のメソッドを提供することで、`Image` クラスの機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="1dc7d-106"><xref:System.Drawing.Imaging.Metafile> クラスは、ベクター イメージの記録および検証のための追加のメソッドを提供することで、`Image` クラスの機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1dc7d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1dc7d-107">In This Section</span></span>  
 [<span data-ttu-id="1dc7d-108">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="1dc7d-108">Types of Bitmaps</span></span>](types-of-bitmaps.md)  
 <span data-ttu-id="1dc7d-109">さまざまなイメージ形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="1dc7d-110">GDI+ でのメタファイル</span><span class="sxs-lookup"><span data-stu-id="1dc7d-110">Metafiles in GDI+</span></span>](metafiles-in-gdi.md)  
 <span data-ttu-id="1dc7d-111">メタファイルの GDI + サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-111">Discusses GDI+ support for metafiles.</span></span>  
  
 [<span data-ttu-id="1dc7d-112">GDI+ でのイメージの描画、配置、およびクローン作成</span><span class="sxs-lookup"><span data-stu-id="1dc7d-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="1dc7d-113">マネージド コードを使用して、ベクター イメージとラスター イメージを描画するためのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="1dc7d-114">GDI+ でのイメージのトリミングおよびスケーリング</span><span class="sxs-lookup"><span data-stu-id="1dc7d-114">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="1dc7d-115">マネージド コードを使用して、ベクター イメージとラスター イメージのトリミングとスケーリングのためのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1dc7d-116">リファレンス</span><span class="sxs-lookup"><span data-stu-id="1dc7d-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="1dc7d-117">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="1dc7d-118">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1dc7d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dc7d-119">Related Sections</span></span>  
 [<span data-ttu-id="1dc7d-120">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="1dc7d-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="1dc7d-121">アプリケーションでイメージを使用する方法を説明するトピックへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1dc7d-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
