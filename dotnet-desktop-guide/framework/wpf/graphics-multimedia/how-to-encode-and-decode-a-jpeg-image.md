---
title: '方法: JPEG イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 0f64ef8537f22ea996cbcf274885de1f3968267a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985904"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="1cac3-102">方法: JPEG イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="1cac3-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="1cac3-103">次の例では、特定の <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> オブジェクトと <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> オブジェクトを使用して、JPEG イメージをデコードおよびエンコードする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1cac3-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="1cac3-104">例 - JPEG イメージをデコードする</span><span class="sxs-lookup"><span data-stu-id="1cac3-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="1cac3-105">この例では、<xref:System.IO.FileStream> の <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> を使用して JPEG イメージをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1cac3-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="1cac3-106">例 - JPEG イメージをエンコードする</span><span class="sxs-lookup"><span data-stu-id="1cac3-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="1cac3-107">この例では、<xref:System.Windows.Media.Imaging.JpegBitmapEncoder> を使用して <xref:System.Windows.Media.Imaging.BitmapSource> を JPEG イメージにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1cac3-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1cac3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cac3-108">See also</span></span>

- [<span data-ttu-id="1cac3-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="1cac3-109">Imaging Overview</span></span>](imaging-overview.md)
