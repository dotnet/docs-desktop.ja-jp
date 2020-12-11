---
title: '方法: 領域でクリッピングを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981239"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="db872-102">方法: 領域でクリッピングを使用する</span><span class="sxs-lookup"><span data-stu-id="db872-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="db872-103">クラスのプロパティの1つ <xref:System.Drawing.Graphics> はクリップ領域です。</span><span class="sxs-lookup"><span data-stu-id="db872-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="db872-104">特定のオブジェクトによって実行 <xref:System.Drawing.Graphics> されるすべての描画は、そのオブジェクトのクリップ領域に制限され <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="db872-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="db872-105">クリップ領域は、メソッドを呼び出すことによって設定でき <xref:System.Drawing.Graphics.SetClip%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="db872-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db872-106">例</span><span class="sxs-lookup"><span data-stu-id="db872-106">Example</span></span>  
 <span data-ttu-id="db872-107">次の例では、1つの多角形で構成されるパスを構築します。</span><span class="sxs-lookup"><span data-stu-id="db872-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="db872-108">次に、そのパスに基づいて、領域を構築します。</span><span class="sxs-lookup"><span data-stu-id="db872-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="db872-109">領域は <xref:System.Drawing.Graphics.SetClip%2A> オブジェクトのメソッドに渡され、 <xref:System.Drawing.Graphics> 2 つの文字列が描画されます。</span><span class="sxs-lookup"><span data-stu-id="db872-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="db872-110">次の図は、クリップされた文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="db872-110">The following illustration shows the clipped strings:</span></span>  
  
 ![クリップされた文字列を示すスクリーンショット。](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db872-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="db872-112">Compiling the Code</span></span>  
 <span data-ttu-id="db872-113">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="db872-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db872-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="db872-114">See also</span></span>

- [<span data-ttu-id="db872-115">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="db872-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="db872-116">領域の使用</span><span class="sxs-lookup"><span data-stu-id="db872-116">Using Regions</span></span>](using-regions.md)
