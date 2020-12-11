---
title: '方法: PNG イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
ms.openlocfilehash: 0a0a2f2625901f7ee32ba9fe70e71681a1b9ccd3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985044"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="3cb53-102">方法: PNG イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="3cb53-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="3cb53-103">次の例では、特定の <xref:System.Windows.Media.Imaging.PngBitmapDecoder> オブジェクトと <xref:System.Windows.Media.Imaging.PngBitmapEncoder> オブジェクトを使用して、ポータブル ネットワーク グラフィックス (PNG) イメージをデコードおよびエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3cb53-103">The following examples show how to decode and encode a Portable Network Graphics (PNG) image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb53-104">例</span><span class="sxs-lookup"><span data-stu-id="3cb53-104">Example</span></span>  
 <span data-ttu-id="3cb53-105">この例では、<xref:System.IO.FileStream> の <xref:System.Windows.Media.Imaging.PngBitmapDecoder> を使用して PNG イメージをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3cb53-105">This example demonstrates how to decode a PNG image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="3cb53-106">例</span><span class="sxs-lookup"><span data-stu-id="3cb53-106">Example</span></span>  
 <span data-ttu-id="3cb53-107">この例では、<xref:System.Windows.Media.Imaging.PngBitmapEncoder> を使用して <xref:System.Windows.Media.Imaging.BitmapSource> を PNG イメージにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3cb53-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a PNG image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3cb53-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cb53-108">See also</span></span>

- [<span data-ttu-id="3cb53-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="3cb53-109">Imaging Overview</span></span>](imaging-overview.md)
