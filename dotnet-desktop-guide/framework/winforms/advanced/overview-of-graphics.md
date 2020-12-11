---
title: グラフィックスについて
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: e2cc534c32c24f3ac13248bd16b177205e480820
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979765"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="a4eaf-102">グラフィックスについて</span><span class="sxs-lookup"><span data-stu-id="a4eaf-102">Overview of Graphics</span></span>
<span data-ttu-id="a4eaf-103">GDI + は、Microsoft Windows オペレーティングシステムのサブシステムを形成するアプリケーションプログラミングインターフェイス (API) です。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="a4eaf-104">GDI + は、画面やプリンターに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="a4eaf-105">名前が示すように、gdi + は GDI の後継であり、グラフィックスデバイスインターフェイス以前のバージョンの Windows に含まれています。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="a4eaf-106">マネージド クラスのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4eaf-106">Managed Class Interface</span></span>  
 <span data-ttu-id="a4eaf-107">GDI + API は、マネージコードとして配置されたクラスのセットを介して公開されます。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="a4eaf-108">この一連のクラスは、GDI + に対する *マネージクラスインターフェイス* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="a4eaf-109">次の名前空間は、マネージド クラスのインターフェイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="a4eaf-110">GDI + などのグラフィックスデバイスインターフェイスを使用すると、特定のディスプレイデバイスの詳細を気にせずに、画面やプリンターに情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="a4eaf-111">プログラマは、GDI + クラスによって提供されるメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="a4eaf-112">次に、これらのメソッドで、特定のデバイス ドライバーへの適切な呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="a4eaf-113">GDI + は、アプリケーションをグラフィックスハードウェアから分離します。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="a4eaf-114">この分離により、プログラマがデバイスに依存しないアプリケーションを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a4eaf-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4eaf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4eaf-115">See also</span></span>

- [<span data-ttu-id="a4eaf-116">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="a4eaf-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
