---
title: 座標
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974709"
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="b8a7e-102">Windows フォームの座標</span><span class="sxs-lookup"><span data-stu-id="b8a7e-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="b8a7e-103">Windows フォームの座標系はデバイス座標に基づいており、Windows フォームで描画するときの基本的な測定単位はデバイス単位 (通常はピクセル) です。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="b8a7e-104">画面上の点は、x 座標と y 座標のペアで表されます。 x 座標は右に上がり、y 座標は上から下に増加します。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="b8a7e-105">画面を基準とした原点の位置は、画面またはクライアントの座標を指定するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="b8a7e-106">画面座標</span><span class="sxs-lookup"><span data-stu-id="b8a7e-106">Screen Coordinates</span></span>  
 <span data-ttu-id="b8a7e-107">Windows フォームアプリケーションでは、画面上のウィンドウの位置を画面座標で指定します。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="b8a7e-108">画面座標の場合、原点は画面の左上隅になります。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="b8a7e-109">ウィンドウの完全な位置は、 <xref:System.Drawing.Rectangle> ウィンドウの左上隅と右下隅を定義する2つの点の画面座標を含む構造体によって記述されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="b8a7e-110">クライアント座標</span><span class="sxs-lookup"><span data-stu-id="b8a7e-110">Client Coordinates</span></span>  
 <span data-ttu-id="b8a7e-111">Windows フォームアプリケーションは、クライアント座標を使用して、フォームまたはコントロール内の点の位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="b8a7e-112">クライアント座標の原点は、コントロールまたはフォームのクライアント領域の左上隅です。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="b8a7e-113">クライアント座標は、画面上のフォームまたはコントロールの位置に関係なく、フォームまたはコントロールに描画するときに、アプリケーションが一貫した座標値を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="b8a7e-114">クライアント領域のサイズは、その <xref:System.Drawing.Rectangle> 領域のクライアント座標を含む構造体によっても記述されます。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="b8a7e-115">いずれの場合も、四角形の左上の座標はクライアント領域に含まれ、右下の座標は除外されます。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="b8a7e-116">グラフィックス操作には、クライアント領域の右端と下端は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="b8a7e-117">たとえば、メソッドは、 <xref:System.Drawing.Graphics.FillRectangle%2A> 指定された四角形の右端と下端までを格納しますが、これらの端は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="b8a7e-118">ある種類の座標から別の型へのマッピング</span><span class="sxs-lookup"><span data-stu-id="b8a7e-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="b8a7e-119">場合によっては、画面座標からクライアント座標にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="b8a7e-120">これは、 <xref:System.Windows.Forms.Control.PointToClient%2A> <xref:System.Windows.Forms.Control.PointToScreen%2A> クラスで使用可能なメソッドとメソッドを使用して簡単に実行でき <xref:System.Windows.Forms.Control> ます。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="b8a7e-121">たとえば、 <xref:System.Windows.Forms.Control.MousePosition%2A> のプロパティ <xref:System.Windows.Forms.Control> は画面座標で報告されますが、これらをクライアント座標に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="b8a7e-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a7e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8a7e-122">See also</span></span>

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
