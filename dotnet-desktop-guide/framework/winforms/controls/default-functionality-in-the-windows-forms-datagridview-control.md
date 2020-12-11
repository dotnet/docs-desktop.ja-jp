---
title: DataGridView コントロールの既定の機能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974204"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="00a84-102">Windows フォーム DataGridView コントロールの既定の機能</span><span class="sxs-lookup"><span data-stu-id="00a84-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="00a84-103">Windows フォームコントロールでは、 <xref:System.Windows.Forms.DataGridView> ユーザーは大量の既定機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="00a84-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="00a84-104">既定の機能</span><span class="sxs-lookup"><span data-stu-id="00a84-104">Default Functionality</span></span>  
 <span data-ttu-id="00a84-105">既定では、 <xref:System.Windows.Forms.DataGridView> コントロールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="00a84-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="00a84-106">テーブルが垂直方向にスクロールしても表示されたままの列ヘッダーと行ヘッダーを自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="00a84-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="00a84-107">には、現在の行の選択インジケーターを含む行ヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="00a84-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="00a84-108">最初のセルに選択範囲の四角形があります。</span><span class="sxs-lookup"><span data-stu-id="00a84-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="00a84-109">ユーザーが列の区切り線をダブルクリックすると、自動的にサイズを変更できる列があります。</span><span class="sxs-lookup"><span data-stu-id="00a84-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="00a84-110">は、 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> アプリケーションのメソッドからメソッドが呼び出されたときに、WINDOWS XP と Windows Server 2003 ファミリの visual スタイルを自動的にサポートし `Main` ます。</span><span class="sxs-lookup"><span data-stu-id="00a84-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="00a84-111">また、既定では、コントロールの内容を <xref:System.Windows.Forms.DataGridView> 編集できます。</span><span class="sxs-lookup"><span data-stu-id="00a84-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="00a84-112">ユーザーがセル内で F2 キーをダブルクリックまたは押すと、コントロールはセルを自動的に編集モードにし、ユーザーの入力に応じてセルの内容を更新します。</span><span class="sxs-lookup"><span data-stu-id="00a84-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="00a84-113">ユーザーがグリッドの最後までスクロールすると、新しいレコードを追加するための行が存在することがわかります。</span><span class="sxs-lookup"><span data-stu-id="00a84-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="00a84-114">ユーザーがこの行をクリックすると、コントロールに新しい行が追加され、 <xref:System.Windows.Forms.DataGridView> 既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="00a84-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="00a84-115">ユーザーが ESC キーを押すと、この新しい行は消えます。</span><span class="sxs-lookup"><span data-stu-id="00a84-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="00a84-116">ユーザーが行ヘッダーをクリックすると、行全体が選択されます。</span><span class="sxs-lookup"><span data-stu-id="00a84-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="00a84-117">コントロールをデータソースにバインドするときに、 <xref:System.Windows.Forms.DataGridView> そのプロパティを設定して、 <xref:System.Windows.Forms.DataGridView.DataSource%2A> コントロールを次のようにします。</span><span class="sxs-lookup"><span data-stu-id="00a84-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="00a84-118">では、データソースの列の名前が列ヘッダーのテキストとして自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="00a84-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="00a84-119">には、データソースの内容が設定されます。</span><span class="sxs-lookup"><span data-stu-id="00a84-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="00a84-120"><xref:System.Windows.Forms.DataGridView> 列は、データソースの各列に対して自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="00a84-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="00a84-121">テーブル内の表示されている各行に対して行を作成します。</span><span class="sxs-lookup"><span data-stu-id="00a84-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="00a84-122">は、ユーザーが列ヘッダーをクリックしたときに、基になるデータに基づいて行を自動的に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="00a84-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a84-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="00a84-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="00a84-124">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="00a84-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
