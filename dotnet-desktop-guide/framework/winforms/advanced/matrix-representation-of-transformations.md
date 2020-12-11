---
title: 変換の行列表現
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981691"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="cadad-102">変換の行列表現</span><span class="sxs-lookup"><span data-stu-id="cadad-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="cadad-103">M × n マトリックスは、m 行と n 列に配置された一連の数値です。</span><span class="sxs-lookup"><span data-stu-id="cadad-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="cadad-104">次の図は、いくつかのマトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="cadad-105">![変換](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="cadad-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="cadad-106">個々の要素を追加することにより、同じサイズの2つのマトリックスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="cadad-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="cadad-107">次の図は、マトリックスの加算の2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="cadad-108">![変換](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="cadad-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="cadad-109">M × n 行列は n × p 行列で乗算でき、結果は m × p 行列になります。</span><span class="sxs-lookup"><span data-stu-id="cadad-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="cadad-110">最初の行列の列数は、2番目の行列の行の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cadad-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="cadad-111">たとえば、4×2行列を2×3行列で乗算すると、4×3行列が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cadad-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="cadad-112">平面内の点とマトリックスの行と列は、ベクターと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="cadad-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="cadad-113">たとえば、(2, 5) は2つのコンポーネントを持つベクターで、(3, 7, 1) は3つのコンポーネントを持つベクターです。</span><span class="sxs-lookup"><span data-stu-id="cadad-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="cadad-114">2つのベクトルのドット積は、次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="cadad-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="cadad-115">(a, b) • (c, d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="cadad-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="cadad-116">(a, b, c) • (d, e, f) = ad + be + cf</span><span class="sxs-lookup"><span data-stu-id="cadad-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="cadad-117">たとえば、(2, 3) と (5, 4) のドット積は (2) (5) + (3) (4) = 22 です。</span><span class="sxs-lookup"><span data-stu-id="cadad-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="cadad-118">(2, 5, 1) と (4, 3, 1) のドット積は、(2) (4) + (5) (3) + (1) (1) = 24 です。</span><span class="sxs-lookup"><span data-stu-id="cadad-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="cadad-119">2つのベクトルのドット積は、別のベクトルではなく、数値であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cadad-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="cadad-120">また、2つのベクトルのコンポーネント数が同じ場合にのみ、ドット積を計算することができます。</span><span class="sxs-lookup"><span data-stu-id="cadad-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="cadad-121">I、j) を i 行目と jth 列のマトリックス A のエントリにします。</span><span class="sxs-lookup"><span data-stu-id="cadad-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="cadad-122">たとえば、A (3, 2) は、第3行のマトリックス A と2番目の列のエントリです。</span><span class="sxs-lookup"><span data-stu-id="cadad-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="cadad-123">A、B、および C がマトリックスで、AB = C であるとします。C のエントリは次のように計算されます。</span><span class="sxs-lookup"><span data-stu-id="cadad-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="cadad-124">C (i, j) = (A の行 i) • (B の列 j)</span><span class="sxs-lookup"><span data-stu-id="cadad-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="cadad-125">次の図は、マトリックス乗算のいくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="cadad-126">![変換](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="cadad-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="cadad-127">平面内のポイントが1×2行列であると考えられる場合は、2×2行列を乗算することによってその点を変換できます。</span><span class="sxs-lookup"><span data-stu-id="cadad-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="cadad-128">次の図は、点 (2, 1) に適用されるいくつかの変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="cadad-129">![変換](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="cadad-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="cadad-130">前の図に示されているすべての変換は、線形変換です。</span><span class="sxs-lookup"><span data-stu-id="cadad-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="cadad-131">平行移動などの特定の変換は線形的ではなく、2×2行列で乗算として表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cadad-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="cadad-132">たとえば、ポイント (2, 1) で開始し、90°回転し、x 方向に3単位を平行移動し、y 方向に4単位を平行移動するとします。</span><span class="sxs-lookup"><span data-stu-id="cadad-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="cadad-133">これを行うには、マトリックス乗算を使用し、その後にマトリックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="cadad-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="cadad-134">![変換](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="cadad-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="cadad-135">線形変換 (2 ×2行列による乗算) の後に平行移動 (1 ×2行列の追加) は、アフィン変換と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cadad-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="cadad-136">1組の行列 (線形部用および平行移動用) にアフィン変換を格納する代わりに、3×3行列に変換全体を格納します。</span><span class="sxs-lookup"><span data-stu-id="cadad-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="cadad-137">この作業を行うには、プレーンのポイントをダミーの3番目の座標で1×3の行列に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cadad-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="cadad-138">通常の方法では、すべての3番目の座標を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="cadad-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="cadad-139">たとえば、ポイント (2, 1) は、マトリックス [2 1 1] によって表されます。</span><span class="sxs-lookup"><span data-stu-id="cadad-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="cadad-140">次の図は、1つの3×3行列で乗算として表現されたアフィン変換 (90 °回転、x 方向の3単位、y 方向の4単位) を示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="cadad-141">![変換](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="cadad-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="cadad-142">前の例では、点 (2, 1) がポイント (2, 6) にマップされています。</span><span class="sxs-lookup"><span data-stu-id="cadad-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="cadad-143">3×3マトリックスの3番目の列には、0、0、1の数値が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cadad-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="cadad-144">これは、アフィン変換の3×3行列の場合に常に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="cadad-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="cadad-145">重要な数値は、列1および2の6つの数値です。</span><span class="sxs-lookup"><span data-stu-id="cadad-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="cadad-146">マトリックスの左上の2×2部分は、変換の線形部分を表し、3番目の行の最初の2つのエントリは変換を表します。</span><span class="sxs-lookup"><span data-stu-id="cadad-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="cadad-147">![変換](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="cadad-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="cadad-148">GDI + では、オブジェクトにアフィン変換を格納でき <xref:System.Drawing.Drawing2D.Matrix> ます。</span><span class="sxs-lookup"><span data-stu-id="cadad-148">In GDI+ you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="cadad-149">アフィン変換を表す行列の3番目の列は常に (0, 0, 1) であるため、オブジェクトを構築するときに、最初の2つの列のうち6つの数値のみを指定し <xref:System.Drawing.Drawing2D.Matrix> ます。</span><span class="sxs-lookup"><span data-stu-id="cadad-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="cadad-150">ステートメントは、 `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` 前の図に示されているマトリックスを構築します。</span><span class="sxs-lookup"><span data-stu-id="cadad-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="cadad-151">複合変換</span><span class="sxs-lookup"><span data-stu-id="cadad-151">Composite Transformations</span></span>  
 <span data-ttu-id="cadad-152">複合変換は、変換のシーケンスであり、その後にもう1つ続きます。</span><span class="sxs-lookup"><span data-stu-id="cadad-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="cadad-153">次の一覧にあるマトリックスと変換について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="cadad-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cadad-154">マトリックス A</span><span class="sxs-lookup"><span data-stu-id="cadad-154">Matrix A</span></span>|<span data-ttu-id="cadad-155">90°回転</span><span class="sxs-lookup"><span data-stu-id="cadad-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="cadad-156">マトリックス B</span><span class="sxs-lookup"><span data-stu-id="cadad-156">Matrix B</span></span>|<span data-ttu-id="cadad-157">X 方向に2の係数でスケールする</span><span class="sxs-lookup"><span data-stu-id="cadad-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="cadad-158">マトリックス C</span><span class="sxs-lookup"><span data-stu-id="cadad-158">Matrix C</span></span>|<span data-ttu-id="cadad-159">Y 方向に3単位を平行移動する</span><span class="sxs-lookup"><span data-stu-id="cadad-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="cadad-160">マトリックス [2 1 1] で表される point (2, 1) を使用して開始し、A に乗算した場合、B、C のように、ポイント (2, 1) は、上記の順序で3つの変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="cadad-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="cadad-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="cadad-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="cadad-162">複合変換の3つの部分を3つの独立した行列に格納するのではなく、A、B、および C を組み合わせて、複合変換全体を格納する1つの3×3行列を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="cadad-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="cadad-163">ABC = D とします。次に、D を乗算したポイントは、A、B、C の順に乗算した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="cadad-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="cadad-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="cadad-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="cadad-165">次の図は、A、B、C、D というマトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="cadad-166">![変換](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="cadad-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="cadad-167">複合変換の行列は、個々の変換行列を乗算することで形成できます。つまり、アフィン変換の任意のシーケンスを1つのオブジェクトに格納でき <xref:System.Drawing.Drawing2D.Matrix> ます。</span><span class="sxs-lookup"><span data-stu-id="cadad-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="cadad-168">複合変換の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="cadad-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="cadad-169">一般に、回転、スケーリング、および平行移動はスケールと同じではなく、回転してから平行移動します。</span><span class="sxs-lookup"><span data-stu-id="cadad-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="cadad-170">同様に、行列乗算の順序も重要です。</span><span class="sxs-lookup"><span data-stu-id="cadad-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="cadad-171">一般に、ABC は... と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="cadad-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="cadad-172">クラスには <xref:System.Drawing.Drawing2D.Matrix> 、複合変換を構築するためのメソッドがいくつか用意されています。、、 <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A> 、、 <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A> <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A> <xref:System.Drawing.Drawing2D.Matrix.Scale%2A> <xref:System.Drawing.Drawing2D.Matrix.Shear%2A> 、および <xref:System.Drawing.Drawing2D.Matrix.Translate%2A> です。</span><span class="sxs-lookup"><span data-stu-id="cadad-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="cadad-173">次の例では、最初に30°を回転させてから y 方向の係数2でスケールし、x 方向に5つの単位を平行移動する複合変換の行列を作成します。</span><span class="sxs-lookup"><span data-stu-id="cadad-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="cadad-174">次の図は、マトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cadad-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="cadad-175">![変換](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="cadad-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cadad-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="cadad-176">See also</span></span>

- [<span data-ttu-id="cadad-177">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="cadad-177">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="cadad-178">マネージド GDI+ での変換の使用</span><span class="sxs-lookup"><span data-stu-id="cadad-178">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
