---
title: '方法: Point4D 構造体が等価かどうかをテストする'
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983252"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="c6bcb-102">方法: Point4D 構造体が等価かどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="c6bcb-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="c6bcb-103">この例では、<xref:System.Windows.Media.Media3D.Point4D> 構造体の等価性と非等価性をテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6bcb-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="c6bcb-104">次のコードは、<xref:System.Windows.Media.Media3D.Point4D> 等価性メソッドを利用し、<xref:System.Windows.Media.Media3D.Point4D> 構造体の等価性と非等価性をテストする方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="c6bcb-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="c6bcb-105"><xref:System.Windows.Media.Media3D.Point4D> 構造体の等価性がオーバーロードされた等価性 (`==`) 演算子でテストされ、その後、オーバーロードされた非等価性 (`!=`) 演算子で非等価性がテストされ、最後に、静的 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> メソッドを利用し、<xref:System.Windows.Media.Media3D.Point3D> 構造体と <xref:System.Windows.Media.Media3D.Point4D> 構造体の等価性が確認されます。</span><span class="sxs-lookup"><span data-stu-id="c6bcb-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6bcb-106">例</span><span class="sxs-lookup"><span data-stu-id="c6bcb-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="c6bcb-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6bcb-107">See also</span></span>

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
