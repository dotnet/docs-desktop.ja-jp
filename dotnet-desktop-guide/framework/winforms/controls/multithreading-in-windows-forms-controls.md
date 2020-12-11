---
title: コントロールでのマルチスレッド
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980602"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="f6866-102">Windows フォーム コントロールのマルチスレッド処理</span><span class="sxs-lookup"><span data-stu-id="f6866-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="f6866-103">多くのアプリケーションでは、別のスレッドで時間のかかる操作を実行することで、ユーザーインターフェイス (UI) の応答性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="f6866-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="f6866-104"><xref:System.Threading>名前空間、メソッド、コンポーネントなど、Windows フォームコントロールのマルチスレッドでは、さまざまなツールを使用でき <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> `BackgroundWorker` ます。</span><span class="sxs-lookup"><span data-stu-id="f6866-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6866-105">コンポーネントは、 `BackgroundWorker` 名前空間とメソッドに置き換えられ、機能を追加します。 <xref:System.Threading> <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> ただし、これらは下位互換性と将来の使用の両方のために保持されます (選択した場合)。</span><span class="sxs-lookup"><span data-stu-id="f6866-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="f6866-106">詳細については、「 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6866-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6866-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f6866-107">In This Section</span></span>  
 [<span data-ttu-id="f6866-108">方法: Windows フォーム コントロールのスレッド セーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="f6866-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="f6866-109">Windows フォームコントロールに対してスレッドセーフな呼び出しを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6866-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="f6866-110">方法: バックグラウンド スレッドを使用してファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="f6866-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="f6866-111">名前空間とメソッドを使用して、 <xref:System.Threading> <xref:System.Windows.Forms.Control.BeginInvoke%2A> ファイルを非同期的に検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6866-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f6866-112">リファレンス</span><span class="sxs-lookup"><span data-stu-id="f6866-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="f6866-113">非同期操作のワーカースレッドをカプセル化するコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f6866-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="f6866-114">サウンドを非同期に読み込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f6866-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="f6866-115">画像を非同期に読み込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f6866-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f6866-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6866-116">Related Sections</span></span>  
 [<span data-ttu-id="f6866-117">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="f6866-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="f6866-118">コンポーネントで時間のかかる操作を実行する方法について説明 <xref:System.ComponentModel.BackgroundWorker> します。</span><span class="sxs-lookup"><span data-stu-id="f6866-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="f6866-119">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="f6866-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="f6866-120">コンポーネントを非同期操作に使用する方法について説明するトピックを示し <xref:System.ComponentModel.BackgroundWorker> ます。</span><span class="sxs-lookup"><span data-stu-id="f6866-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
