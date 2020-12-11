---
title: DataGridView コントロールのシナリオ
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 160d967c6445fb753cb6c73babfb02a734a07e28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974209"
---
# <a name="datagridview-control-scenarios-windows-forms"></a><span data-ttu-id="ad0c2-102">DataGridView コントロールのシナリオ (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ad0c2-102">DataGridView Control Scenarios (Windows Forms)</span></span>
<span data-ttu-id="ad0c2-103">コントロールを使用 <xref:System.Windows.Forms.DataGridView> すると、さまざまなデータソースの表形式のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-103">With the <xref:System.Windows.Forms.DataGridView> control, you can display tabular data from a variety of data sources.</span></span> <span data-ttu-id="ad0c2-104">簡単に使用できるように、を手動で設定 <xref:System.Windows.Forms.DataGridView> し、コントロールを介して直接データを操作できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-104">For simple uses, you can manually populate a <xref:System.Windows.Forms.DataGridView> and manipulate the data directly through the control.</span></span> <span data-ttu-id="ad0c2-105">ただし、通常は、外部データソースにデータを格納し、コンポーネントを通じてコントロールをバインドし <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-105">Typically, however, you will store your data in an external data source and bind the control to it through a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="ad0c2-106">このトピックでは、コントロールに関連する一般的なシナリオのいくつかについて説明し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-106">This topic describes some of the common scenarios that involve the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a><span data-ttu-id="ad0c2-107">シナリオ 1: 少量のデータを表示する</span><span class="sxs-lookup"><span data-stu-id="ad0c2-107">Scenario 1: Displaying Small Amounts of Data</span></span>  
 <span data-ttu-id="ad0c2-108">外部データソースにデータを格納して、コントロールに表示する必要はありません <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-108">You do not have to store your data in an external data source to display it in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ad0c2-109">少量のデータを処理している場合は、コントロールを自分で設定し、コントロールを使用してデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-109">If you are working with a small amount of data, you can populate the control yourself and manipulate the data through the control.</span></span> <span data-ttu-id="ad0c2-110">これは *非バインドモード* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-110">This is called *unbound mode*.</span></span> <span data-ttu-id="ad0c2-111">詳細については、「方法: バインドされていない [Windows フォーム DataGridView コントロールを作成](how-to-create-an-unbound-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-111">For more information, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="ad0c2-112">シナリオのキーポイント</span><span class="sxs-lookup"><span data-stu-id="ad0c2-112">Scenario Key Points</span></span>  
  
- <span data-ttu-id="ad0c2-113">非バインドモードでは、コントロールを手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-113">In unbound mode, you populate the control manually.</span></span>  
  
- <span data-ttu-id="ad0c2-114">非バインドモードは、読み取り専用の少量のデータに特に適しています。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-114">Unbound mode is particularly suited for small amounts of read-only data.</span></span>  
  
- <span data-ttu-id="ad0c2-115">非バインドモードは、スプレッドシートに似た、または少ないに設定されたテーブルにも適しています。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-115">Unbound mode is also suited for spreadsheet-like or sparsely populated tables.</span></span>  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a><span data-ttu-id="ad0c2-116">シナリオ 2: 外部データソースに格納されているデータの表示と更新</span><span class="sxs-lookup"><span data-stu-id="ad0c2-116">Scenario 2: Viewing and Updating Data Stored in an External Data Source</span></span>  
 <span data-ttu-id="ad0c2-117"><xref:System.Windows.Forms.DataGridView>このコントロールをユーザーインターフェイス (UI) として使用すると、ユーザーは、データベーステーブルやビジネスオブジェクトのコレクションなどのデータソースに保存されているデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-117">You can use the <xref:System.Windows.Forms.DataGridView> control as a user interface (UI) through which users can access data kept in a data source such as a database table or a collection of business objects.</span></span> <span data-ttu-id="ad0c2-118">詳細については、「 [方法: データを Windows フォーム DataGridView コントロールにバインドする](how-to-bind-data-to-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-118">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="ad0c2-119">シナリオのキーポイント</span><span class="sxs-lookup"><span data-stu-id="ad0c2-119">Scenario Key Points</span></span>  
  
- <span data-ttu-id="ad0c2-120">バインドモードを使用すると、データソースに接続したり、データソースのプロパティまたはデータベースの列に基づいて自動的に列を生成したり、コントロールを自動的に設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-120">Bound mode lets you connect to a data source, automatically generate columns based on the data source properties or database columns, and automatically populate the control.</span></span>  
  
- <span data-ttu-id="ad0c2-121">バインドモードは、ユーザーがデータを操作する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-121">Bound mode is suited for heavy user interaction with data.</span></span> <span data-ttu-id="ad0c2-122">データは、表示用に書式設定できます。ユーザー指定のデータは、データソースによって予期される形式に解析できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-122">Data can be formatted for display, and user-specified data can be parsed into the format expected by the data source.</span></span> <span data-ttu-id="ad0c2-123">データ入力のフォーマットエラーとデータベース制約エラーを検出すると、ユーザーに警告が表示され、間違ったセルを修正できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-123">Data entry formatting errors and database constraint errors can be detected so that users can be warned and erroneous cells can be corrected.</span></span>  
  
- <span data-ttu-id="ad0c2-124">列の並べ替え、固定、並べ替えなどの追加機能を使用すると、ユーザーはワークフローにとって最も便利な方法でデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-124">Additional functionality such as column sorting, freezing, and reordering enable users to view data in the way most convenient for their workflow.</span></span>  
  
- <span data-ttu-id="ad0c2-125">クリップボードのサポートにより、ユーザーはアプリケーションから他のアプリケーションにデータをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-125">Clipboard support enables users to copy data from your application into other applications.</span></span>  
  
## <a name="scenario-3-advanced-data"></a><span data-ttu-id="ad0c2-126">シナリオ 3: 高度なデータ</span><span class="sxs-lookup"><span data-stu-id="ad0c2-126">Scenario 3: Advanced Data</span></span>  
 <span data-ttu-id="ad0c2-127">標準のデータバインディングモデルでは対応できない特別なニーズがある場合は、 *仮想モード* を実装することで、コントロールとデータの間の相互作用を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-127">If you have special needs that the standard data binding model does not address, you can manage the interaction between the control and your data by implementing *virtual mode*.</span></span> <span data-ttu-id="ad0c2-128">仮想モードの実装とは、情報が必要なときにコントロールがセルに関する情報を要求できるようにする1つ以上のイベントハンドラーを実装することを意味します。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-128">Implementing virtual mode means implementing one or more event handlers that let the control request information about cells as the information is needed.</span></span>  
  
 <span data-ttu-id="ad0c2-129">たとえば、大量のデータを処理する場合は、最適な効率を得るために仮想モードを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-129">For example, if you work with large amounts of data, you may want to implement virtual mode to ensure optimal efficiency.</span></span> <span data-ttu-id="ad0c2-130">仮想モードは、別のデータソースから取得した列と共に表示される非バインド列の値を維持する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-130">Virtual mode is also useful for maintaining the values of unbound columns that you display along with columns retrieved from another data source.</span></span>  
  
 <span data-ttu-id="ad0c2-131">仮想モードの詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-131">For more information about virtual mode, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="ad0c2-132">シナリオのキーポイント</span><span class="sxs-lookup"><span data-stu-id="ad0c2-132">Scenario Key Points</span></span>  
  
- <span data-ttu-id="ad0c2-133">仮想モードは、パフォーマンスを微調整する必要がある場合に非常に大量のデータを表示するために適しています。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-133">Virtual mode is suited for displaying very large amounts of data when you need to fine-tune performance.</span></span>  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a><span data-ttu-id="ad0c2-134">シナリオ 4: 行と列のサイズを自動的に変更する</span><span class="sxs-lookup"><span data-stu-id="ad0c2-134">Scenario 4: Automatically Resizing Rows and Columns</span></span>  
 <span data-ttu-id="ad0c2-135">定期的に更新されるデータを表示すると、行と列のサイズを自動的に変更して、すべてのコンテンツが表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-135">When you display data that is regularly updated, you can automatically resize rows and columns to ensure that all content is visible.</span></span> <span data-ttu-id="ad0c2-136">コントロールには、手動による <xref:System.Windows.Forms.DataGridView> サイズ変更を有効または無効にしたり、特定の時刻にプログラムによってサイズを変更したり、コンテンツが変更されるたびに自動的にサイズを変更したりするためのオプション</span><span class="sxs-lookup"><span data-stu-id="ad0c2-136">The <xref:System.Windows.Forms.DataGridView> control provides several options that let you enable or disable manual resizing, resize programmatically at specific times, or resize automatically whenever content changes.</span></span> <span data-ttu-id="ad0c2-137">詳細については、「 [Windows フォーム DataGridView コントロールのサイズ変更オプション](sizing-options-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-137">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="ad0c2-138">シナリオのキーポイント</span><span class="sxs-lookup"><span data-stu-id="ad0c2-138">Scenario Key Points</span></span>  
  
- <span data-ttu-id="ad0c2-139">手動でサイズ変更することで、ユーザーはセルの高さと幅を調整できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-139">Manual resizing enables users to adjust cell heights and widths.</span></span>  
  
- <span data-ttu-id="ad0c2-140">自動サイズ変更を使用すると、セルのサイズを維持して、セルの内容がクリップされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-140">Automatic resizing enables you to maintain cell sizes so that cell content is never clipped.</span></span>  
  
- <span data-ttu-id="ad0c2-141">プログラムによるサイズ変更では、連続する自動サイズ変更のパフォーマンスが低下しないように、特定の時間にセルのサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-141">Programmatic resizing enables you to resize cells at specific times to avoid the performance penalty of continuous automatic resizing.</span></span>  
  
## <a name="scenario-5-simple-customization"></a><span data-ttu-id="ad0c2-142">シナリオ 5: 簡単なカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ad0c2-142">Scenario 5: Simple Customization</span></span>  
 <span data-ttu-id="ad0c2-143"><xref:System.Windows.Forms.DataGridView>コントロールには、基本的な外観と動作を変更するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-143">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to alter its basic appearance and behavior.</span></span> <span data-ttu-id="ad0c2-144">詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-144">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="ad0c2-145">シナリオのキーポイント</span><span class="sxs-lookup"><span data-stu-id="ad0c2-145">Scenario Key Points</span></span>  
  
- <span data-ttu-id="ad0c2-146"><xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを使用すると、色、フォント、書式設定、位置情報を複数のレベルで、またコントロールの個々の要素に対して提供できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-146"><xref:System.Windows.Forms.DataGridViewCellStyle> objects let you provide color, font, formatting, and positioning information at multiple levels and for individual elements of the control.</span></span>  
  
- <span data-ttu-id="ad0c2-147">セルスタイルを複数の要素で重ねて共有して、コードを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-147">Cell styles can be layered and shared by multiple elements, letting you reuse code.</span></span>  
  
## <a name="scenario-6-advanced-customization"></a><span data-ttu-id="ad0c2-148">シナリオ 6: 高度なカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ad0c2-148">Scenario 6: Advanced Customization</span></span>  
 <span data-ttu-id="ad0c2-149"><xref:System.Windows.Forms.DataGridView>コントロールには、外観と動作をカスタマイズするためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-149">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to customize its appearance and behavior.</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="ad0c2-150">シナリオのキーポイント</span><span class="sxs-lookup"><span data-stu-id="ad0c2-150">Scenario Key Points</span></span>  
  
- <span data-ttu-id="ad0c2-151">独自のセルの描画コードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-151">You can provide your own cell painting code.</span></span> <span data-ttu-id="ad0c2-152">詳細については、「 [方法: Windows フォーム DataGridView コントロールのセルの外観をカスタマイズする](customize-the-appearance-of-cells-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-152">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="ad0c2-153">独自の行の描画を提供できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-153">You can provide your own row painting.</span></span> <span data-ttu-id="ad0c2-154">これは、複数の列にまたがるコンテンツを含む行を作成する場合などに便利です。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-154">This is useful, for example, to create rows with content that spans multiple columns.</span></span> <span data-ttu-id="ad0c2-155">詳細については、「 [方法: Windows フォーム DataGridView コントロールの行の外観をカスタマイズする](customize-the-appearance-of-rows-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-155">For more information, see [How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control](customize-the-appearance-of-rows-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="ad0c2-156">独自のセルおよび列クラスを実装して、セルの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-156">You can implement your own cell and column classes to customize cell appearance.</span></span> <span data-ttu-id="ad0c2-157">詳細については、「 [方法: 動作と外観を拡張して Windows フォーム DataGridView コントロールのセルと列をカスタマイズする](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-157">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).</span></span>  
  
- <span data-ttu-id="ad0c2-158">組み込みの列型によって提供されるもの以外のコントロールをホストするために、独自のセルクラスおよび列クラスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-158">You can implement your own cell and column classes to host controls other than the ones provided by the built-in column types.</span></span> <span data-ttu-id="ad0c2-159">詳細については、「 [方法: Windows フォーム DataGridView セルのコントロールをホストする](how-to-host-controls-in-windows-forms-datagridview-cells.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0c2-159">For more information, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0c2-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad0c2-160">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ad0c2-161">DataGridView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ad0c2-161">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
