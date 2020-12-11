---
title: GDI+ マネージド コードについて
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, about GDI+
- GDI+
- graphics [Windows Forms], GDI+
ms.assetid: a98a76ab-e455-49c9-891c-0491ac932f2c
ms.openlocfilehash: db47a63bc11961faf852215e954dda62c594bbe5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974913"
---
# <a name="about-gdi-managed-code"></a><span data-ttu-id="0be44-102">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="0be44-102">About GDI+ Managed Code</span></span>

<span data-ttu-id="0be44-103">GDI + は、2次元のベクターグラフィックス、イメージング、およびタイポグラフィを提供する Windows オペレーティングシステムの部分です。</span><span class="sxs-lookup"><span data-stu-id="0be44-103">GDI+ is the portion of the Windows operating system that provides two-dimensional vector graphics, imaging, and typography.</span></span> <span data-ttu-id="0be44-104">Gdi + では、新しい機能を追加し、既存の機能を最適化することによって、GDI (以前のバージョンの Windows に含まれているグラフィックスデバイスインターフェイス) が強化されています。</span><span class="sxs-lookup"><span data-stu-id="0be44-104">GDI+ improves on GDI (the Graphics Device Interface included with earlier versions of Windows) by adding new features and by optimizing existing features.</span></span>

<span data-ttu-id="0be44-105">GDI + マネージクラスインターフェイス (一連のラッパー) は、XML Web サービスやその他のアプリケーションをビルド、配置、および実行するための環境である .NET Framework の一部です。</span><span class="sxs-lookup"><span data-stu-id="0be44-105">The GDI+ managed class interface (a set of wrappers) is part of the .NET Framework, an environment for building, deploying, and running XML Web services and other applications.</span></span>

<span data-ttu-id="0be44-106">ここでは、マネージコードを使用するプログラマのための GDI + API について説明します。</span><span class="sxs-lookup"><span data-stu-id="0be44-106">This section provides information about the GDI+ API for programmers using managed code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0be44-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0be44-107">In this section</span></span>

- [<span data-ttu-id="0be44-108">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="0be44-108">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)  
 <span data-ttu-id="0be44-109">ベクター グラフィックスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0be44-109">Discusses vector graphics.</span></span>

- [<span data-ttu-id="0be44-110">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="0be44-110">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="0be44-111">使用可能なイメージの種類とそれらを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0be44-111">Discusses the type of images available and how to work with them.</span></span>

- [<span data-ttu-id="0be44-112">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="0be44-112">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)  
 <span data-ttu-id="0be44-113">GDI + を使用してグラフィックスを変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0be44-113">Discusses how to transform graphics with GDI+.</span></span>

## <a name="reference"></a><span data-ttu-id="0be44-114">リファレンス</span><span class="sxs-lookup"><span data-stu-id="0be44-114">Reference</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-115">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-115">Describes this class and has links to all its members.</span></span>

- <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-116">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-116">Describes this class and has links to all its members.</span></span>

- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-117">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-117">Describes this class and has links to all its members.</span></span>
  
- <xref:System.Drawing.Imaging.Metafile?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-118">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-118">Describes this class and has links to all its members.</span></span>

- <xref:System.Drawing.Font?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-119">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-119">Describes this class and has links to all its members.</span></span>

- <xref:System.Drawing.Brush?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-120">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-120">Describes this class and has links to all its members.</span></span>

- <xref:System.Drawing.Color?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-121">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-121">Describes this class and has links to all its members.</span></span>

- <xref:System.Drawing.Drawing2D.Matrix?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-122">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-122">Describes this class and has links to all its members.</span></span>

- <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>  
 <span data-ttu-id="0be44-123">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0be44-123">Describes this class and has links to all its members.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0be44-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0be44-124">Related sections</span></span>

<span data-ttu-id="0be44-125">[マネージグラフィックスクラスの使用](using-managed-graphics-classes.md)</span><span class="sxs-lookup"><span data-stu-id="0be44-125">[Using Managed Graphics Classes](using-managed-graphics-classes.md)</span></span>\
<span data-ttu-id="0be44-126">`Graphics` プログラミング インターフェイスを使用する方法を説明するトピックへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0be44-126">Contains links to topics that demonstrate how to use the `Graphics` programming interface.</span></span>
