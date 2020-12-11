---
title: '方法: サムネイルとしてイメージを読み込む'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: a5b2f4b7de52203ded711e9e829886a5c25c6067
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983068"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="2bdad-102">方法: サムネイルとしてイメージを読み込む</span><span class="sxs-lookup"><span data-stu-id="2bdad-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="2bdad-103">次の例は、<xref:System.Windows.Controls.Image> をサムネイルとして読み込み、アプリケーション メモリを節約する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2bdad-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bdad-104">例</span><span class="sxs-lookup"><span data-stu-id="2bdad-104">Example</span></span>  
 <span data-ttu-id="2bdad-105">次の例では、イメージの読み込みに必要なメモリを減らすために、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] で <xref:System.Windows.Media.Imaging.BitmapImage> の <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2bdad-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="2bdad-106">例</span><span class="sxs-lookup"><span data-stu-id="2bdad-106">Example</span></span>  
 <span data-ttu-id="2bdad-107">次の例では、イメージの読み込みに必要なメモリを減らすために、コードで <xref:System.Windows.Media.Imaging.BitmapImage> の <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2bdad-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="2bdad-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bdad-108">See also</span></span>

- [<span data-ttu-id="2bdad-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="2bdad-109">Imaging Overview</span></span>](imaging-overview.md)
