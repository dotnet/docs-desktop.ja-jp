---
title: '方法: インストールされたエンコーダーの一覧'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981828"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="49ffa-102">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="49ffa-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="49ffa-103">アプリケーションが特定のイメージファイル形式に保存できるかどうかを判断するために、コンピューターで使用可能なイメージエンコーダーを一覧表示することができます。</span><span class="sxs-lookup"><span data-stu-id="49ffa-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="49ffa-104">クラスには静的メソッドが用意されて <xref:System.Drawing.Imaging.ImageCodecInfo> <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> いるため、使用できるイメージエンコーダーを特定できます。</span><span class="sxs-lookup"><span data-stu-id="49ffa-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="49ffa-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.ImageCodecInfo> ます。</span><span class="sxs-lookup"><span data-stu-id="49ffa-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ffa-106">例</span><span class="sxs-lookup"><span data-stu-id="49ffa-106">Example</span></span>  
 <span data-ttu-id="49ffa-107">次のコード例では、インストールされているエンコーダーとそのプロパティ値の一覧を出力します。</span><span class="sxs-lookup"><span data-stu-id="49ffa-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49ffa-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="49ffa-108">Compiling the Code</span></span>  
 <span data-ttu-id="49ffa-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49ffa-109">This example requires:</span></span>  
  
- <span data-ttu-id="49ffa-110">Windows フォーム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="49ffa-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="49ffa-111"><xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="49ffa-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ffa-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="49ffa-112">See also</span></span>

- [<span data-ttu-id="49ffa-113">方法: インストールされたデコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="49ffa-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="49ffa-114">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="49ffa-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
