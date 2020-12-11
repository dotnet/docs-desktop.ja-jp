---
title: グラフィックス サービスの 3 つのカテゴリ
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975226"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="90226-102">グラフィックス サービスの 3 つのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="90226-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="90226-103">Windows フォームのグラフィックスオファリングは、次の3つの広範なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="90226-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
- <span data-ttu-id="90226-104">2次元 (2-d) ベクターグラフィックス</span><span class="sxs-lookup"><span data-stu-id="90226-104">Two-dimensional (2-D) vector graphics</span></span>  
  
- <span data-ttu-id="90226-105">イメージング</span><span class="sxs-lookup"><span data-stu-id="90226-105">Imaging</span></span>  
  
- <span data-ttu-id="90226-106">文字体裁</span><span class="sxs-lookup"><span data-stu-id="90226-106">Typography</span></span>  
  
## <a name="2d-vector-graphics"></a><span data-ttu-id="90226-107">2D ベクターグラフィックス</span><span class="sxs-lookup"><span data-stu-id="90226-107">2D Vector Graphics</span></span>  
 <span data-ttu-id="90226-108">直線、曲線、および図形などの2次元ベクターグラフィックスは、座標系の点のセットによって指定されるプリミティブです。</span><span class="sxs-lookup"><span data-stu-id="90226-108">Two-dimensional vector graphics, such as lines, curves, and figures, are primitives that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="90226-109">たとえば、直線は2つのエンドポイントによって指定され、四角形は、左上隅の位置と幅と高さを示す数値のペアを指定する点によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="90226-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="90226-110">単純なパスは、直線で結ばれた点の配列によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="90226-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="90226-111">ベジエスプラインは、4つのコントロールポイントによって指定された高度な曲線です。</span><span class="sxs-lookup"><span data-stu-id="90226-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 <span data-ttu-id="90226-112">GDI + には、プリミティブ自体、プリミティブの描画方法に関する情報を格納するクラス、および実際に描画を実行するクラスに関する情報を格納するクラスと構造体が用意されています。</span><span class="sxs-lookup"><span data-stu-id="90226-112">GDI+ provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="90226-113">たとえば、 <xref:System.Drawing.Rectangle> 構造体は四角形の位置とサイズを格納します。 <xref:System.Drawing.Pen> クラスは、線の色、線の幅、および線のスタイルに関する情報を格納し <xref:System.Drawing.Graphics> ます。クラスには、線、四角形、パス、およびその他の図形を描画するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="90226-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="90226-114">また、 <xref:System.Drawing.Brush> 閉じた図形とパスに色またはパターンを設定する方法に関する情報を格納するクラスもいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="90226-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="90226-115">ベクターイメージ (グラフィックスコマンドのシーケンス) をメタファイルに記録できます。</span><span class="sxs-lookup"><span data-stu-id="90226-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> <span data-ttu-id="90226-116">GDI + には、 <xref:System.Drawing.Imaging.Metafile> メタファイルの記録、表示、および保存のためのクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="90226-116">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="90226-117">クラスとクラスを使用すると、 <xref:System.Drawing.Imaging.MetafileHeader> <xref:System.Drawing.Imaging.MetaHeader> メタファイルヘッダーに格納されているデータを検査できます。</span><span class="sxs-lookup"><span data-stu-id="90226-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="90226-118">イメージング</span><span class="sxs-lookup"><span data-stu-id="90226-118">Imaging</span></span>  
 <span data-ttu-id="90226-119">ベクターグラフィックスの手法では、特定の種類の画像を表示するのは困難または不可能です。</span><span class="sxs-lookup"><span data-stu-id="90226-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="90226-120">たとえば、ツールバーボタンの画像やアイコンとして表示される画像は、直線や曲線のコレクションとして指定するのが困難です。</span><span class="sxs-lookup"><span data-stu-id="90226-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="90226-121">混雑している野球スタジアムの高解像度デジタル写真は、ベクター手法を使用した作成がさらに困難です。</span><span class="sxs-lookup"><span data-stu-id="90226-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="90226-122">この種類のイメージはビットマップとして格納されます。これは、画面上の個々のドットの色を表す数値の配列です。</span><span class="sxs-lookup"><span data-stu-id="90226-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> <span data-ttu-id="90226-123">GDI + には、 <xref:System.Drawing.Bitmap> ビットマップを表示、操作、および保存するためのクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="90226-123">GDI+ provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="90226-124">文字体裁</span><span class="sxs-lookup"><span data-stu-id="90226-124">Typography</span></span>  
 <span data-ttu-id="90226-125">タイポグラフィは、さまざまなフォント、サイズ、スタイルでテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="90226-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> <span data-ttu-id="90226-126">GDI + は、この複雑なタスクを広範にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="90226-126">GDI+ provides extensive support for this complex task.</span></span> <span data-ttu-id="90226-127">GDI + の新機能の1つは、サブピクセルアンチエイリアシングです。これにより、LCD 画面に表示されるテキストがより滑らかになります。</span><span class="sxs-lookup"><span data-stu-id="90226-127">One of the new features in GDI+ is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="90226-128">さらに、Windows フォームには、クラスの GDI 機能を使用してテキストを描画するオプションが用意されて <xref:System.Windows.Forms.TextRenderer> います。</span><span class="sxs-lookup"><span data-stu-id="90226-128">In addition, Windows Forms offers the option to draw text with GDI capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90226-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="90226-129">See also</span></span>

- [<span data-ttu-id="90226-130">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="90226-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="90226-131">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="90226-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="90226-132">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="90226-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
