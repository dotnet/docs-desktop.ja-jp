---
title: GDI+ でのメタファイル
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979771"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="148ce-102">GDI+ でのメタファイル</span><span class="sxs-lookup"><span data-stu-id="148ce-102">Metafiles in GDI+</span></span>
<span data-ttu-id="148ce-103">GDI + には、 <xref:System.Drawing.Imaging.Metafile> メタファイルを記録および表示できるようにクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="148ce-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="148ce-104">メタファイルは、ベクターイメージとも呼ばれ、一連の描画コマンドと設定として格納されるイメージです。</span><span class="sxs-lookup"><span data-stu-id="148ce-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="148ce-105">オブジェクトに記録されたコマンドと設定は、 <xref:System.Drawing.Imaging.Metafile> メモリに格納することも、ファイルまたはストリームに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="148ce-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="148ce-106">メタファイル形式</span><span class="sxs-lookup"><span data-stu-id="148ce-106">Metafile Formats</span></span>  
 <span data-ttu-id="148ce-107">GDI + では、次の形式で格納されたメタファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="148ce-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="148ce-108">Windows メタファイル (WMF)</span><span class="sxs-lookup"><span data-stu-id="148ce-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="148ce-109">拡張メタファイル (EMF)</span><span class="sxs-lookup"><span data-stu-id="148ce-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="148ce-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="148ce-110">EMF+</span></span>  
  
 <span data-ttu-id="148ce-111">GDI + では、EMF および EMF + 形式でメタファイルを記録できますが、WMF 形式では記録できません。</span><span class="sxs-lookup"><span data-stu-id="148ce-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="148ce-112">EMF + は、GDI + レコードを格納できる EMF の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="148ce-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="148ce-113">EMF + 形式には、EMF + のみと EMF + Dual の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="148ce-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="148ce-114">EMF + 唯一のメタファイルには GDI + レコードのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="148ce-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="148ce-115">このようなメタファイルは GDI + によって表示できますが、GDI では表示できません。</span><span class="sxs-lookup"><span data-stu-id="148ce-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="148ce-116">EMF + デュアルメタファイルには、GDI + および GDI レコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="148ce-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="148ce-117">EMF + デュアルメタファイル内の各 GDI + レコードは、代替 GDI レコードとペアになります。</span><span class="sxs-lookup"><span data-stu-id="148ce-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="148ce-118">このようなメタファイルは、GDI + または GDI によって表示できます。</span><span class="sxs-lookup"><span data-stu-id="148ce-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="148ce-119">次の例では、以前にファイルとして保存されたメタファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="148ce-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="148ce-120">メタファイルは、(100, 100) の左上隅に表示されます。</span><span class="sxs-lookup"><span data-stu-id="148ce-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="148ce-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="148ce-121">See also</span></span>

- [<span data-ttu-id="148ce-122">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="148ce-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
