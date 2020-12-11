---
title: '方法: バックグラウンドで操作を実行する'
description: BackgroundWorker クラスを使用して、バックグラウンドで時間のかかる Windows フォーム操作を実行する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 6b2a97f5acf1e906dfe141aee62e99a4e50dca9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974753"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="62717-103">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="62717-103">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="62717-104">完了に長い時間がかかる操作を実行しており、ユーザー インターフェイスで遅延が発生しないようにするには<xref:System.ComponentModel.BackgroundWorker> クラスを使用して別のスレッドで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="62717-104">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="62717-105">次のコード例は、バック グラウンドで時間のかかる操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="62717-105">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="62717-106">フォームには、**[開始]** ボタンと **[キャンセル]** ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="62717-106">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="62717-107">非同期操作を実行するには、**[開始]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="62717-107">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="62717-108">実行中の非同期操作を停止するには、**[キャンセル]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="62717-108">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="62717-109">各操作の結果は、<xref:System.Windows.Forms.MessageBox> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="62717-109">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="62717-110">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="62717-110">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="62717-111">「[チュートリアル: 操作をバックグラウンドで実行する](walkthrough-running-an-operation-in-the-background.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="62717-111">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62717-112">例</span><span class="sxs-lookup"><span data-stu-id="62717-112">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="62717-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="62717-113">Compiling the Code</span></span>  
 <span data-ttu-id="62717-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="62717-114">This example requires:</span></span>  
  
- <span data-ttu-id="62717-115">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="62717-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62717-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="62717-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="62717-117">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="62717-117">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="62717-118">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="62717-118">BackgroundWorker Component</span></span>](backgroundworker-component.md)
