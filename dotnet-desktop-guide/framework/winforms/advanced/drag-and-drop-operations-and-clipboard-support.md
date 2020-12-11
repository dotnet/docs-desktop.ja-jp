---
title: ドラッグ アンド ドロップ操作とクリップボードのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: 5e7bb75b648163dab7e410a159d55ebbb75f1b0a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975033"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="8dd4a-102">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="8dd4a-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="8dd4a-103">一連のイベントを処理することで、Windows ベースのアプリケーション内でユーザーによるドラッグ アンド ドロップ操作を有効にすることができます。最も顕著なのは <xref:System.Windows.Forms.Control.DragEnter>、<xref:System.Windows.Forms.Control.DragLeave>、および <xref:System.Windows.Forms.Control.DragDrop> のイベントです。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="8dd4a-104">単純なメソッドの呼び出しを使用して、Windows ベースのアプリケーション内で、ユーザーの切り取り/コピー/貼り付けのサポートや、ユーザー データの転送を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8dd4a-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8dd4a-105">In This Section</span></span>  
 [<span data-ttu-id="8dd4a-106">チュートリアル: Windows フォームにおけるドラッグ アンド ドロップ操作の実行</span><span class="sxs-lookup"><span data-stu-id="8dd4a-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="8dd4a-107">ドラッグ アンド ドロップ操作を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="8dd4a-108">方法: アプリケーション間でドラッグ アンド ドロップ操作を実行する</span><span class="sxs-lookup"><span data-stu-id="8dd4a-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="8dd4a-109">アプリケーション間でドラッグ アンド ドロップ操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="8dd4a-110">方法: クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="8dd4a-110">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="8dd4a-111">プログラムを使用して、クリップボードの情報を挿入する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="8dd4a-112">方法: クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="8dd4a-112">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="8dd4a-113">クリップボードに保存されているデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8dd4a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dd4a-114">Related Sections</span></span>  
 [<span data-ttu-id="8dd4a-115">Windows フォームにおけるドラッグ アンド ドロップ機能</span><span class="sxs-lookup"><span data-stu-id="8dd4a-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="8dd4a-116">ドラッグ アンド ドロップの動作を実装するために使用されるメソッド、イベント、およびクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="8dd4a-117">ドラッグ操作を続行するためにアクセス許可を確認する複雑なイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="8dd4a-118">ドラッグ操作を開始するときに中心となる複雑なメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="8dd4a-119">「 [方法: アクティブな MDI 子にデータを送信する](how-to-send-data-to-the-active-mdi-child.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dd4a-119">Also see [How to: Send Data to the Active MDI Child](how-to-send-data-to-the-active-mdi-child.md).</span></span>
