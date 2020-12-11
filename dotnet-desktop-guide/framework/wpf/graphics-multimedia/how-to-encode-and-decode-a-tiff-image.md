---
title: '方法: TIFF イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 173a30e785b16a3617b82b771c463083356d6e6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984731"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="816c2-102">方法: TIFF イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="816c2-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="816c2-103">次の例では、特定の <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> オブジェクトと <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> オブジェクトを使用して、Tagged Image File Format (TIFF) イメージをデコードおよびエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="816c2-103">The following examples show how to decode and encode a Tagged Image File Format (TIFF) image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="816c2-104">例</span><span class="sxs-lookup"><span data-stu-id="816c2-104">Example</span></span>  
 <span data-ttu-id="816c2-105">この例では、<xref:System.Uri> の <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> を使用して TIFF イメージをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="816c2-105">This example demonstrates how to decode a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="816c2-106">例</span><span class="sxs-lookup"><span data-stu-id="816c2-106">Example</span></span>  
 <span data-ttu-id="816c2-107">この例では、<xref:System.Windows.Media.Imaging.TiffBitmapEncoder> を使用して <xref:System.Windows.Media.Imaging.BitmapSource> を TIFF イメージにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="816c2-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="816c2-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="816c2-108">See also</span></span>

- [<span data-ttu-id="816c2-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="816c2-109">Imaging Overview</span></span>](imaging-overview.md)
