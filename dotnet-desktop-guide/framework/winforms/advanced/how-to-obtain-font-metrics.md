---
title: '方法: フォント メトリックを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981807"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="9e758-102">方法: フォント メトリックを取得する</span><span class="sxs-lookup"><span data-stu-id="9e758-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="9e758-103">クラスには、 <xref:System.Drawing.FontFamily> 特定のファミリ/スタイルの組み合わせに対してさまざまなメトリックを取得する次のメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9e758-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
- <span data-ttu-id="9e758-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="9e758-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="9e758-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="9e758-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="9e758-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="9e758-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="9e758-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="9e758-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="9e758-108">これらのメソッドによって返される値はフォントデザイン単位であるため、特定のオブジェクトのサイズと単位に依存し <xref:System.Drawing.Font> ません。</span><span class="sxs-lookup"><span data-stu-id="9e758-108">The values returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="9e758-109">次の図は、さまざまなメトリックを示しています。</span><span class="sxs-lookup"><span data-stu-id="9e758-109">The following illustration shows the various metrics:</span></span>
  
 ![フォントメトリックの図: アセント、降下、および行間。](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a><span data-ttu-id="9e758-111">例</span><span class="sxs-lookup"><span data-stu-id="9e758-111">Example</span></span>  
 <span data-ttu-id="9e758-112">次の例では、Arial フォントファミリの標準スタイルのメトリックを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e758-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="9e758-113">また、このコードでは、 <xref:System.Drawing.Font> 16 ピクセルのサイズで (Arial ファミリに基づく) オブジェクトを作成し、その特定のオブジェクトのメトリック (ピクセル単位) を表示し <xref:System.Drawing.Font> ます。</span><span class="sxs-lookup"><span data-stu-id="9e758-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="9e758-114">次の図は、コード例の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e758-114">The following illustration shows the output of the example code:</span></span>
  
 ![Arial フォントメトリックのコード出力の例。](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 <span data-ttu-id="9e758-116">前の図の出力の最初の2行に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9e758-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="9e758-117"><xref:System.Drawing.Font>オブジェクトは16のサイズを返し、オブジェクトは <xref:System.Drawing.FontFamily> em の高さ2048を返します。</span><span class="sxs-lookup"><span data-stu-id="9e758-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="9e758-118">この2つの数値 (16 と 2048) は、オブジェクトのフォントデザイン単位と単位 (この場合はピクセル) を変換するためのキーです <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="9e758-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="9e758-119">たとえば、次のようにして、アセントをデザイン単位からピクセルに変換できます。</span><span class="sxs-lookup"><span data-stu-id="9e758-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 ![デザイン単位からピクセルへの変換を示す数式](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 <span data-ttu-id="9e758-121">次のコードでは、オブジェクトのデータメンバーを設定することによってテキストを垂直方向に配置し <xref:System.Drawing.PointF.Y%2A> <xref:System.Drawing.PointF> ます。</span><span class="sxs-lookup"><span data-stu-id="9e758-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="9e758-122">Y 座標は、 `font.Height` テキストの新しい行ごとにによって増加します。</span><span class="sxs-lookup"><span data-stu-id="9e758-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="9e758-123"><xref:System.Drawing.Font.Height%2A>オブジェクトのプロパティは、 <xref:System.Drawing.Font> その特定のオブジェクトの行間 (ピクセル単位) を返し <xref:System.Drawing.Font> ます。</span><span class="sxs-lookup"><span data-stu-id="9e758-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="9e758-124">この例では、によって返される数値 <xref:System.Drawing.Font.Height%2A> は19です。</span><span class="sxs-lookup"><span data-stu-id="9e758-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="9e758-125">これは、行間隔メトリックをピクセルに変換することによって取得された (整数に切り上げられた) 数値と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9e758-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="9e758-126">Em の高さ (サイズまたは em サイズとも呼ばれます) は、アセントと降下の合計ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9e758-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="9e758-127">アセントと降下の合計は、セルの高さと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9e758-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="9e758-128">セルの高さから内部の先頭を引いた値が em の高さと同じになります。</span><span class="sxs-lookup"><span data-stu-id="9e758-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="9e758-129">セルの高さに外部の先頭を加えた値は、行間と同じになります。</span><span class="sxs-lookup"><span data-stu-id="9e758-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e758-130">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9e758-130">Compiling the Code</span></span>  
 <span data-ttu-id="9e758-131">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="9e758-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e758-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e758-132">See also</span></span>

- [<span data-ttu-id="9e758-133">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="9e758-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9e758-134">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="9e758-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
