---
title: グラフィックス コンテナーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975225"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="f3ed6-102">グラフィックス コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="f3ed6-102">Using Graphics Containers</span></span>
<span data-ttu-id="f3ed6-103">オブジェクトには <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A> ベクターイメージ、ラスターイメージ、およびテキストを表示するための、、およびなどのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="f3ed6-104"><xref:System.Drawing.Graphics>オブジェクトには、描画される項目の品質と向きに影響を与えるいくつかのプロパティもあります。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="f3ed6-105">たとえば、スムージングモードプロパティは、アンチエイリアシングが線と曲線に適用されるかどうかを決定し、ワールド変換プロパティは描画される項目の位置と回転に影響します。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="f3ed6-106"><xref:System.Drawing.Graphics>オブジェクトは、特定のディスプレイデバイスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="f3ed6-107">オブジェクトを使用して <xref:System.Drawing.Graphics> ウィンドウに描画すると、 <xref:System.Drawing.Graphics> オブジェクトもその特定のウィンドウに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="f3ed6-108">オブジェクトは、 <xref:System.Drawing.Graphics> 描画に影響を与える一連のプロパティを保持し、デバイス固有の情報にリンクされるため、コンテナーと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="f3ed6-109">既存 <xref:System.Drawing.Graphics> のオブジェクトのメソッドを呼び出すことによって、既存のオブジェクト内にセカンダリコンテナーを作成でき <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3ed6-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f3ed6-110">In This Section</span></span>  
 [<span data-ttu-id="f3ed6-111">Graphics オブジェクトの状態の管理</span><span class="sxs-lookup"><span data-stu-id="f3ed6-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="f3ed6-112">オブジェクトの品質設定、クリッピング領域、および変換を管理する方法について説明し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="f3ed6-113">入れ子になっているグラフィックス コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="f3ed6-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="f3ed6-114">コンテナーを使用してオブジェクトの状態を制御する方法について説明し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="f3ed6-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
