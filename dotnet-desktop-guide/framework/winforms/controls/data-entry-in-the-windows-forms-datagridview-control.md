---
title: DataGridView コントロールでのデータ入力
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: e95095624f45cc1507735083a87293730e9133e9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974227"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2ade5-102">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="2ade5-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2ade5-103">`DataGridView`コントロールには、ユーザーがコントロールのデータを追加または変更する方法を変更できる機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="2ade5-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="2ade5-104">たとえば、新しい行に既定値を指定し、エラーが発生した場合にユーザーに警告することにより、データ入力の効率を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="2ade5-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ade5-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2ade5-105">In This Section</span></span>  
 [<span data-ttu-id="2ade5-106">方法: Windows フォーム DataGridView コントロールの編集モードを指定する</span><span class="sxs-lookup"><span data-stu-id="2ade5-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2ade5-107">ユーザーがセルの編集を開始する方法を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="2ade5-108">方法: Windows フォーム DataGridView コントロールの新しい行に既定値を指定する</span><span class="sxs-lookup"><span data-stu-id="2ade5-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="2ade5-109">データ入力時間を節約するために、新しいレコードの行を事前に作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="2ade5-110">Windows フォーム DataGridView コントロールにおける新規レコード行の使用</span><span class="sxs-lookup"><span data-stu-id="2ade5-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2ade5-111">新しいレコードの行について説明します。詳細については、非表示にする方法、外観をカスタマイズする方法、およびコレクションに関連付ける方法についても説明し <xref:System.Windows.Forms.DataGridView.Rows%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2ade5-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="2ade5-112">チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="2ade5-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2ade5-113">データ入力の書式設定エラーを防ぐために、ユーザー入力を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="2ade5-114">チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="2ade5-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="2ade5-115">ユーザーが新しい値をコミットしようとしたときにデータソースから発生したデータ入力エラーを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ade5-116">リファレンス</span><span class="sxs-lookup"><span data-stu-id="2ade5-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2ade5-117"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2ade5-118">プロパティに関するリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.EditMode%2A> します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="2ade5-119">イベントのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="2ade5-120">イベントのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.DataError> します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="2ade5-121">イベントのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.CellValidating> します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2ade5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ade5-122">Related Sections</span></span>  
 [<span data-ttu-id="2ade5-123">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="2ade5-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2ade5-124">手動または外部データソースからコントロールにデータを設定する方法を説明するトピックを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ade5-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ade5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ade5-125">See also</span></span>

- [<span data-ttu-id="2ade5-126">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="2ade5-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2ade5-127">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="2ade5-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
