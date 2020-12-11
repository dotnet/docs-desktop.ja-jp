---
title: '方法: 装飾を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983335"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="2d6b3-102">方法: 装飾を実装する</span><span class="sxs-lookup"><span data-stu-id="2d6b3-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="2d6b3-103">この例は、最小限の装飾の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d6b3-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="2d6b3-104">実装側の注意</span><span class="sxs-lookup"><span data-stu-id="2d6b3-104">Notes for Implementers</span></span>  
 <span data-ttu-id="2d6b3-105">装飾自体にはレンダリング動作が備わっていないので、装飾のレンダリングは装飾の実装側の責任で行う必要がある点に、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d6b3-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="2d6b3-106">レンダリング動作を実装する一般的な方法は、(この例で示すように) <xref:System.Windows.UIElement.OnRender%2A> メソッドをオーバーライドし、1 つまたは複数の <xref:System.Windows.Media.DrawingContext> オブジェクトを使用して、必要に応じて装飾のビジュアルをレンダリングすることです。</span><span class="sxs-lookup"><span data-stu-id="2d6b3-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d6b3-107">例</span><span class="sxs-lookup"><span data-stu-id="2d6b3-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2d6b3-108">説明</span><span class="sxs-lookup"><span data-stu-id="2d6b3-108">Description</span></span>  
 <span data-ttu-id="2d6b3-109">抽象型 <xref:System.Windows.Documents.Adorner> クラスから継承されるクラスを実装することにより、カスタム装飾が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2d6b3-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="2d6b3-110">この例の装飾は、<xref:System.Windows.UIElement.OnRender%2A> メソッドをオーバーライドすることで <xref:System.Windows.UIElement> の四隅を円で装飾するだけのものです。</span><span class="sxs-lookup"><span data-stu-id="2d6b3-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2d6b3-111">コード</span><span class="sxs-lookup"><span data-stu-id="2d6b3-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="2d6b3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d6b3-112">See also</span></span>

- [<span data-ttu-id="2d6b3-113">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="2d6b3-113">Adorners Overview</span></span>](adorners-overview.md)
