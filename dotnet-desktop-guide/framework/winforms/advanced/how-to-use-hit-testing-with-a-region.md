---
title: '方法: 領域でヒット テストを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981227"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="5c9b4-102">方法: 領域でヒット テストを使用する</span><span class="sxs-lookup"><span data-stu-id="5c9b4-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="5c9b4-103">ヒットテストの目的は、カーソルが特定のオブジェクト (アイコンやボタンなど) 上にあるかどうかを判断することです。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c9b4-104">例</span><span class="sxs-lookup"><span data-stu-id="5c9b4-104">Example</span></span>  
 <span data-ttu-id="5c9b4-105">次の例では、2つの四角形領域の和集合を形成することによって、正形の領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="5c9b4-106">変数が `point` 最新のクリックの場所を保持していると仮定します。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="5c9b4-107">コードによって、 `point` がプラス形の領域にあるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="5c9b4-108">点が領域内にある場合 (ヒット)、領域は不透明な赤のブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="5c9b4-109">それ以外の場合、領域には半透明の赤のブラシが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c9b4-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5c9b4-110">Compiling the Code</span></span>  
 <span data-ttu-id="5c9b4-111">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="5c9b4-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9b4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c9b4-112">See also</span></span>

- <xref:System.Drawing.Region>
- [<span data-ttu-id="5c9b4-113">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="5c9b4-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="5c9b4-114">方法: 領域でクリッピングを使用する</span><span class="sxs-lookup"><span data-stu-id="5c9b4-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
