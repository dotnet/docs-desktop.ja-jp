---
title: '方法: カラー行列を使用して単一色を変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 2df74e022b842f7e5c9ff80f6aeddfce51af5eab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981751"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="261b3-102">方法: カラー行列を使用して単一色を変換する</span><span class="sxs-lookup"><span data-stu-id="261b3-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
<span data-ttu-id="261b3-103">GDI + には、 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> イメージを格納および操作するためのクラスとクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="261b3-103">GDI+ provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="261b3-104"><xref:System.Drawing.Image><xref:System.Drawing.Bitmap>オブジェクトとオブジェクトには、各ピクセルの色が32ビットの数値として格納されます。各ピクセルは、赤、緑、青、およびアルファにそれぞれ8ビットずつ格納されます。</span><span class="sxs-lookup"><span data-stu-id="261b3-104"><xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="261b3-105">4つの各コンポーネントは、0 ~ 255 の数値です。0は濃度を表し、255は完全な輝度を表します。</span><span class="sxs-lookup"><span data-stu-id="261b3-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="261b3-106">アルファコンポーネントは、色の透明度を指定します。0は完全に透明で、255は完全に不透明です。</span><span class="sxs-lookup"><span data-stu-id="261b3-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="261b3-107">カラーベクターは、(赤、緑、青、アルファ) の形式の4タプルです。</span><span class="sxs-lookup"><span data-stu-id="261b3-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="261b3-108">たとえば、カラーベクター (0、255、0、255) は、赤または青のない不透明色を表しますが、完全に輝度が緑色になっています。</span><span class="sxs-lookup"><span data-stu-id="261b3-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="261b3-109">色を表すためのもう1つの規則では、数値1を使用して完全に輝度を指定します。</span><span class="sxs-lookup"><span data-stu-id="261b3-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="261b3-110">この規則を使用すると、前の段落で説明した色がベクター (0, 1, 0, 1) によって表されます。</span><span class="sxs-lookup"><span data-stu-id="261b3-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> <span data-ttu-id="261b3-111">GDI + では、カラー変換を実行するときに、1の規則を使用して完全な強度を使用します。</span><span class="sxs-lookup"><span data-stu-id="261b3-111">GDI+ uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="261b3-112">カラーベクターに4×4の行列を掛けることによって、線形変換 (回転、拡大縮小、および like) をカラーベクターに適用できます。</span><span class="sxs-lookup"><span data-stu-id="261b3-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="261b3-113">ただし、4×4行列を使用して平行移動 (非線形) を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="261b3-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="261b3-114">ダミーの5番目の座標 (たとえば、数字 1) を各カラーベクターに追加する場合は、5×5行列を使用して、線形変換と翻訳の任意の組み合わせを適用できます。</span><span class="sxs-lookup"><span data-stu-id="261b3-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="261b3-115">線形変換とそれに続く変換で構成される変換は、アフィン変換と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="261b3-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="261b3-116">たとえば、色 (0.2、0.0、0.4、1.0) で開始し、次の変換を適用するとします。</span><span class="sxs-lookup"><span data-stu-id="261b3-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="261b3-117">赤のコンポーネントを2倍にする</span><span class="sxs-lookup"><span data-stu-id="261b3-117">Double the red component</span></span>  
  
2. <span data-ttu-id="261b3-118">赤、緑、および青のコンポーネントに0.2 を追加する</span><span class="sxs-lookup"><span data-stu-id="261b3-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="261b3-119">次の行列乗算では、変換のペアを一覧表示された順序で実行します。</span><span class="sxs-lookup"><span data-stu-id="261b3-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 ![変換乗算行列のスクリーンショット。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 <span data-ttu-id="261b3-121">カラー行列の要素は、行と列によってインデックスが作成されます (0 から始まる)。</span><span class="sxs-lookup"><span data-stu-id="261b3-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="261b3-122">たとえば、マトリックス M の5番目の行と3番目の列のエントリは、M [4] [2] によって示されます。</span><span class="sxs-lookup"><span data-stu-id="261b3-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="261b3-123">次の図に示すように、5×5の id 行列は対角線に1つ、他のすべての場所で0になります。</span><span class="sxs-lookup"><span data-stu-id="261b3-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="261b3-124">Id 行列によってカラーベクターを乗算した場合、カラーベクターは変わりません。</span><span class="sxs-lookup"><span data-stu-id="261b3-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="261b3-125">カラー変換のマトリックスを作成する便利な方法は、id マトリックスから開始し、必要な変換を生成する小さな変更を行うことです。</span><span class="sxs-lookup"><span data-stu-id="261b3-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 ![カラー変換の 5 x 5 の id 行列のスクリーンショット。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 <span data-ttu-id="261b3-127">マトリックスと変換の詳細については、「 [座標系と変換](coordinate-systems-and-transformations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="261b3-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="261b3-128">例</span><span class="sxs-lookup"><span data-stu-id="261b3-128">Example</span></span>  
 <span data-ttu-id="261b3-129">次の例では、1つの色 (0.2、0.0、0.4、1.0) のイメージを取得し、前の段落で説明した変換を適用します。</span><span class="sxs-lookup"><span data-stu-id="261b3-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="261b3-130">次の図は、左側にある元の画像と右側の変換された画像を示しています。</span><span class="sxs-lookup"><span data-stu-id="261b3-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 ![左側に紫色の四角を、右側に fuchsia の四角形を入れます。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 <span data-ttu-id="261b3-132">次の例のコードでは、次の手順を使用して、色の色の色を実行します。</span><span class="sxs-lookup"><span data-stu-id="261b3-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="261b3-133">オブジェクトを初期化 <xref:System.Drawing.Imaging.ColorMatrix> します。</span><span class="sxs-lookup"><span data-stu-id="261b3-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="261b3-134">オブジェクトを作成 <xref:System.Drawing.Imaging.ImageAttributes> し、オブジェクト <xref:System.Drawing.Imaging.ColorMatrix> のメソッドにオブジェクトを渡し <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> <xref:System.Drawing.Imaging.ImageAttributes> ます。</span><span class="sxs-lookup"><span data-stu-id="261b3-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="261b3-135">オブジェクトを <xref:System.Drawing.Imaging.ImageAttributes> <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドに渡し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="261b3-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="261b3-136">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="261b3-136">Compiling the Code</span></span>  
 <span data-ttu-id="261b3-137">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="261b3-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="261b3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="261b3-138">See also</span></span>

- [<span data-ttu-id="261b3-139">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="261b3-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="261b3-140">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="261b3-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
