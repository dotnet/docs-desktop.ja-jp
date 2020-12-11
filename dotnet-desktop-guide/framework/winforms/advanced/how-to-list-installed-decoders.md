---
title: '方法: インストールされたデコーダーの一覧'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981327"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="cba14-102">方法: インストールされたデコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="cba14-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="cba14-103">コンピューターで使用可能なイメージデコーダーを一覧表示して、アプリケーションが特定のイメージファイル形式を読み取ることができるかどうかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="cba14-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="cba14-104">クラスは、 <xref:System.Drawing.Imaging.ImageCodecInfo> <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 使用可能なイメージデコーダーを判別できるように、静的メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cba14-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="cba14-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.ImageCodecInfo> ます。</span><span class="sxs-lookup"><span data-stu-id="cba14-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cba14-106">例</span><span class="sxs-lookup"><span data-stu-id="cba14-106">Example</span></span>  
 <span data-ttu-id="cba14-107">次のコード例では、インストールされているデコーダーとそのプロパティ値の一覧を出力します。</span><span class="sxs-lookup"><span data-stu-id="cba14-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cba14-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cba14-108">Compiling the Code</span></span>  
 <span data-ttu-id="cba14-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cba14-109">This example requires:</span></span>  
  
- <span data-ttu-id="cba14-110">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cba14-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="cba14-111"><xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="cba14-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba14-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="cba14-112">See also</span></span>

- [<span data-ttu-id="cba14-113">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="cba14-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="cba14-114">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="cba14-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
