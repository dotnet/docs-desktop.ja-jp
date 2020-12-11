---
title: '方法: WDP イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: 8c5c312c7e58d48a865e493c38c3defd3f5f3d1d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984728"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="b5459-102">方法: WDP イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="b5459-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="b5459-103">次の例では、特定の <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> オブジェクトと <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> オブジェクトを使用して、Microsoft Windows Media Photo イメージをデコードおよびエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b5459-103">The following examples show how to decode and encode a Microsoft Windows Media Photo image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5459-104">例</span><span class="sxs-lookup"><span data-stu-id="b5459-104">Example</span></span>  
 <span data-ttu-id="b5459-105">この例では、<xref:System.Uri> の <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> を使用して Microsoft Windows Media Photo イメージをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b5459-105">This example demonstrates how to decode a Windows Media Photo image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="b5459-106">例</span><span class="sxs-lookup"><span data-stu-id="b5459-106">Example</span></span>  
 <span data-ttu-id="b5459-107">この例では、<xref:System.Windows.Media.Imaging.WmpBitmapEncoder> を使用して <xref:System.Windows.Media.Imaging.BitmapSource> を Microsoft Windows Media Photo イメージにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b5459-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a Windows Media Photo image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b5459-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5459-108">See also</span></span>

- [<span data-ttu-id="b5459-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="b5459-109">Imaging Overview</span></span>](imaging-overview.md)
