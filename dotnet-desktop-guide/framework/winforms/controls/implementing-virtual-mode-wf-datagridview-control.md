---
title: 'チュートリアル: DataGridView コントロールでの仮想モードの実装'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982971"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="48db5-102">チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードを実装する</span><span class="sxs-lookup"><span data-stu-id="48db5-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="48db5-103">非常に大量の表形式データをコントロールに表示する場合は、 <xref:System.Windows.Forms.DataGridView> プロパティをに設定 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> し、 `true` コントロールとそのデータストアとの対話を明示的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="48db5-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="48db5-104">これにより、このような場合にコントロールのパフォーマンスを微調整できます。</span><span class="sxs-lookup"><span data-stu-id="48db5-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="48db5-105"><xref:System.Windows.Forms.DataGridView>コントロールには、カスタムデータストアと対話するために処理できるいくつかのイベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="48db5-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="48db5-106">このチュートリアルでは、これらのイベントハンドラーを実装する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="48db5-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="48db5-107">このトピックのコード例では、簡単に説明するために、非常に単純なデータソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="48db5-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="48db5-108">運用環境の設定では、通常、表示する必要のある行だけをキャッシュに読み込み、 <xref:System.Windows.Forms.DataGridView> キャッシュとの対話および更新のためのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="48db5-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="48db5-109">詳細については、「 [Windows フォーム DataGridView コントロールでの Just-in-time データ読み込みによる仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48db5-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="48db5-110">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールで仮想モードを実装](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48db5-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="48db5-111">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="48db5-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="48db5-112">仮想モードを実装するには</span><span class="sxs-lookup"><span data-stu-id="48db5-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="48db5-113">から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、コントロールを格納し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="48db5-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="48db5-114">次のコードには、いくつかの基本的な初期化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48db5-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="48db5-115">これは、後の手順で使用されるいくつかの変数を宣言し、メソッドを提供 `Main` し、クラスコンストラクターに単純なフォームレイアウトを提供します。</span><span class="sxs-lookup"><span data-stu-id="48db5-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="48db5-116"><xref:System.Windows.Forms.Form.Load>コントロールを初期化 <xref:System.Windows.Forms.DataGridView> し、データストアにサンプル値を設定するフォームのイベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="48db5-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="48db5-117"><xref:System.Windows.Forms.DataGridView.CellValueNeeded>データストアまたは `Customer` 現在編集中のオブジェクトから要求されたセル値を取得するイベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="48db5-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="48db5-118">このイベント <xref:System.Windows.Forms.DataGridView> は、コントロールがセルを描画する必要があるときに常に発生します。</span><span class="sxs-lookup"><span data-stu-id="48db5-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="48db5-119">編集された <xref:System.Windows.Forms.DataGridView.CellValuePushed> 行を表すオブジェクトに、編集されたセル値を格納するイベントのハンドラーを実装し `Customer` ます。</span><span class="sxs-lookup"><span data-stu-id="48db5-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="48db5-120">このイベントは、ユーザーがセル値の変更をコミットするたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="48db5-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="48db5-121"><xref:System.Windows.Forms.DataGridView.NewRowNeeded>新しく作成された行を表す新しいオブジェクトを作成するイベントのハンドラーを実装し `Customer` ます。</span><span class="sxs-lookup"><span data-stu-id="48db5-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="48db5-122">このイベントは、ユーザーが新しいレコードの行を入力するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="48db5-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="48db5-123"><xref:System.Windows.Forms.DataGridView.RowValidated>新しい行または変更された行をデータストアに保存するイベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="48db5-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="48db5-124">このイベントは、ユーザーが現在の行を変更するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="48db5-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="48db5-125"><xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 編集モードで ESC キーを2回押すか、編集モードの外部で1回押すことによって、ユーザーが行再設定を通知するときにイベントを発生させるかどうかを示すイベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="48db5-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="48db5-126">既定では、 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> イベントハンドラーでプロパティがに設定されていない限り、現在の行のセルが変更されたときに、行再設定に対してが発生し `true` <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> ます。</span><span class="sxs-lookup"><span data-stu-id="48db5-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="48db5-127">このイベントは、実行時にコミットスコープが決定される場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48db5-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="48db5-128"><xref:System.Windows.Forms.DataGridView.CancelRowEdit>現在の行を表すオブジェクトの値を破棄するイベントのハンドラーを実装 `Customer` します。</span><span class="sxs-lookup"><span data-stu-id="48db5-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="48db5-129">このイベントは、編集モードで ESC キーを2回押すか、編集モードの外側で1回押すことによって、ユーザーが行再設定を通知するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="48db5-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="48db5-130">現在の行にセルが変更されていない場合、または <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> `false` イベントハンドラーでプロパティの値がに設定されている場合、このイベントは発生しません <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 。</span><span class="sxs-lookup"><span data-stu-id="48db5-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="48db5-131">イベントのハンドラーを実装 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> します。このハンドラーは、データストアから既存のオブジェクトを削除する `Customer` か、 `Customer` 新しく作成された行を表す未保存のオブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="48db5-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="48db5-132">このイベントは、ユーザーが行ヘッダーをクリックし、DEL キーを押して行を削除するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="48db5-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="48db5-133">`Customers`このコード例で使用されるデータ項目を表す単純なクラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="48db5-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="48db5-134">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="48db5-134">Testing the Application</span></span>  
 <span data-ttu-id="48db5-135">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="48db5-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="48db5-136">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="48db5-136">To test the form</span></span>  
  
- <span data-ttu-id="48db5-137">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="48db5-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="48db5-138"><xref:System.Windows.Forms.DataGridView>3 つの顧客レコードが設定されたコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48db5-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="48db5-139">行の複数のセルの値を変更して、編集モードで ESC キーを2回押すと、編集モードの外に1回押して、行全体を元の値に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="48db5-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="48db5-140">コントロール内の行を変更、追加、または削除すると、 `Customer` データストア内のオブジェクトも変更、追加、または削除されます。</span><span class="sxs-lookup"><span data-stu-id="48db5-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="48db5-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="48db5-141">Next Steps</span></span>  
 <span data-ttu-id="48db5-142">このアプリケーションを使用すると、コントロールに仮想モードを実装するために処理する必要があるイベントについての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="48db5-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="48db5-143">この基本的なアプリケーションは、さまざまな方法で改善できます。</span><span class="sxs-lookup"><span data-stu-id="48db5-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="48db5-144">外部データベースからの値をキャッシュするデータストアを実装します。</span><span class="sxs-lookup"><span data-stu-id="48db5-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="48db5-145">キャッシュは必要に応じて値を取得および破棄する必要があります。これにより、クライアントコンピューターで少量のメモリを消費しているときに、表示に必要なものだけが格納されます。</span><span class="sxs-lookup"><span data-stu-id="48db5-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="48db5-146">要件に応じて、データストアのパフォーマンスを微調整します。</span><span class="sxs-lookup"><span data-stu-id="48db5-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="48db5-147">たとえば、より大きなキャッシュサイズを使用してデータベースクエリの数を最小限に抑えることで、クライアントコンピューターのメモリ制限ではなく、低速のネットワーク接続を補正することができます。</span><span class="sxs-lookup"><span data-stu-id="48db5-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="48db5-148">外部データベースからの値のキャッシュの詳細については、「 [方法: Windows フォーム DataGridView コントロールで Just-in-time データ読み込みを使用して仮想モードを実装する](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48db5-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48db5-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="48db5-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="48db5-150">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="48db5-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="48db5-151">Windows フォーム DataGridView コントロールを拡張するための推奨される手順</span><span class="sxs-lookup"><span data-stu-id="48db5-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="48db5-152">Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装</span><span class="sxs-lookup"><span data-stu-id="48db5-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="48db5-153">方法: Windows フォーム DataGridView コントロールで仮想モードを実装する</span><span class="sxs-lookup"><span data-stu-id="48db5-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
