---
title: '方法: パラメーターとしてジオメトリを使用してヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983075"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="1b84b-102">方法: パラメーターとしてジオメトリを使用してヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="1b84b-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="1b84b-103">この例では、<xref:System.Windows.Media.Geometry> をヒット テスト パラメーターとして使用して、ビジュアル オブジェクトに対してヒット テストを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b84b-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b84b-104">例</span><span class="sxs-lookup"><span data-stu-id="1b84b-104">Example</span></span>  
 <span data-ttu-id="1b84b-105">次の例では、<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> メソッドの <xref:System.Windows.Media.GeometryHitTestParameters> を使用してヒット テストを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b84b-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="1b84b-106">`OnMouseDown` メソッドに渡される <xref:System.Windows.Point> 値は、<xref:System.Windows.Media.Geometry> オブジェクトを作成してヒット テストの範囲を拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b84b-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="1b84b-107"><xref:System.Windows.Media.GeometryHitTestResult> の <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> プロパティは、<xref:System.Windows.Media.Geometry> をヒット テスト パラメーターとして使用するヒット テストの結果に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b84b-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="1b84b-108">ヒット テストのジオメトリ (青い円) と対象のビジュアル オブジェクト (赤い正方形) の描画されるコンテンツとの関係を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1b84b-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![ヒット テストで使用される IntersectionDetail を示す図。](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="1b84b-110"><xref:System.Windows.Media.Geometry> をヒット テスト パラメーターとして使用する場合に、ヒット テストのコールバックを実装する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1b84b-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="1b84b-111">`result` パラメーターは、<xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> プロパティの値を取得するために、<xref:System.Windows.Media.GeometryHitTestResult> にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="1b84b-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="1b84b-112">このプロパティ値を使用すると、<xref:System.Windows.Media.Geometry> ヒット テスト パラメーターの全体または一部が、ヒット テストの対象の、レンダリングされるコンテンツ内に含まれるかどうかを判別することができます。</span><span class="sxs-lookup"><span data-stu-id="1b84b-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="1b84b-113">ここに示すサンプル コードでは、完全に対象の境界内に含まれるビジュアルについてのみ、ヒット テストの結果をリストに追加しています。</span><span class="sxs-lookup"><span data-stu-id="1b84b-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <span data-ttu-id="1b84b-114">交差の詳細が <xref:System.Windows.Media.IntersectionDetail.Empty> の場合は、<xref:System.Windows.Media.HitTestResult> コールバックを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="1b84b-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b84b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b84b-115">See also</span></span>

- [<span data-ttu-id="1b84b-116">ビジュアル層でのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="1b84b-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="1b84b-117">ビジュアル内のジオメトリのヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="1b84b-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
