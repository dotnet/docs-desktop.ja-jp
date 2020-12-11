---
title: DataGridView コントロールでのデザイナーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 50e8bddb97c2dfb84cebdbb2ca4d42a6c5743304
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983932"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="a2ec9-102">Windows フォーム DataGridView コントロールでのデザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="a2ec9-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a2ec9-103">Visual Studio では、コードを `DataGridView` 記述しなくても多くのセットアップタスクを実行できるコントロールに対してデザイナーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="a2ec9-104">これらのタスクには、データソースへのコントロールのバインド、データの表示に使用される列の変更、およびコントロールの外観と基本動作の調整が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2ec9-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a2ec9-105">In This Section</span></span>  
 [<span data-ttu-id="a2ec9-106">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="a2ec9-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-107">[列の **追加** ] および [ **列の編集** ] ダイアログボックスを使用して、列のコレクションにデータを設定したり変更したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="a2ec9-108">方法: デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="a2ec9-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-109">コントロールのスマートタグの [ **データソースの選択** ] オプションを使用してデータに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="a2ec9-110">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の順序を変更する</span><span class="sxs-lookup"><span data-stu-id="a2ec9-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-111">[ **列の編集** ] ダイアログボックスを使用して列を並べ替える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="a2ec9-112">方法: デザイナーを使用して Windows フォーム DataGridView 列の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="a2ec9-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="a2ec9-113">[ **列の編集** ] ダイアログボックスを使用して列の型を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="a2ec9-114">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="a2ec9-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-115">コントロールのスマートタグを使用して、ユーザーが列を再配置できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="a2ec9-116">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="a2ec9-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-117">[ **列の編集** ] ダイアログボックスを使用して、特定の列がスクロールされないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="a2ec9-118">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を非表示にする</span><span class="sxs-lookup"><span data-stu-id="a2ec9-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-119">[ **列の編集** ] ダイアログボックスを使用して特定の列を非表示にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="a2ec9-120">方法: デザイナーを使用して Windows フォームの DataGridView コントロールで列を読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="a2ec9-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-121">[ **列の編集** ] ダイアログボックスを使用して、ユーザーが特定の列の値を編集できないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="a2ec9-122">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="a2ec9-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-123">コントロールのスマートタグを使用して、ユーザーが行を追加または削除できないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="a2ec9-124">方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="a2ec9-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="a2ec9-125">[ **CellStyle ビルダー** ] ダイアログボックスを使用して、コントロールに元帳に似た外観を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="a2ec9-126">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセル スタイルとデータ形式を設定する</span><span class="sxs-lookup"><span data-stu-id="a2ec9-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="a2ec9-127">[ **CellStyle ビルダー** ] ダイアログボックスを使用して、コントロールの基本的な外観とデータ表示形式を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a2ec9-128">リファレンス</span><span class="sxs-lookup"><span data-stu-id="a2ec9-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="a2ec9-129"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="a2ec9-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ec9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ec9-130">See also</span></span>

- [<span data-ttu-id="a2ec9-131">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="a2ec9-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
