---
title: DataGridView コントロールでのデータの表示
description: Windows フォーム DataGridView コントロールを使用して、さまざまな外部データソースのデータを表示する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: a0f3e6627290521b8c10477c31459f1486e79162
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981935"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3e3d1-103">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="3e3d1-103">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3e3d1-104">`DataGridView`コントロールは、さまざまな外部データソースのデータを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-104">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="3e3d1-105">または、コントロールに行と列を追加し、データを手動で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-105">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="3e3d1-106">コントロールをデータソースにバインドすると、データソースのスキーマに基づいて列が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-106">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="3e3d1-107">これらの列が希望どおりに表示されない場合は、それらの列を非表示、削除、または再配置することができます。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-107">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="3e3d1-108">また、非バインド列を追加して、データソースから取得されていない補足データを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-108">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="3e3d1-109">また、標準形式 (通貨形式など) を使用してデータを表示することも、必要に応じてデータを表示するように表示形式をカスタマイズすることもできます (負の数値の背景色を変更する、文字列値を対応するイメージに置き換えるなど)。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-109">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e3d1-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3e3d1-110">In This Section</span></span>  
 [<span data-ttu-id="3e3d1-111">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="3e3d1-111">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-112">コントロールにデータを設定するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-112">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="3e3d1-113">Windows フォーム DataGridView コントロールでのデータの書式設定</span><span class="sxs-lookup"><span data-stu-id="3e3d1-113">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-114">セルの表示値を書式設定するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-114">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="3e3d1-115">チュートリアル: バインドされていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="3e3d1-115">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-116">コントロールにデータを手動で設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-116">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="3e3d1-117">方法: データを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="3e3d1-117">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-118">データベースから取得した情報を含むにバインドすることによって、コントロールにデータを設定する方法について説明し `BindingSource` ます。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-118">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="3e3d1-119">方法: データバインドされた Windows フォーム DataGridView コントロールに列を自動生成する</span><span class="sxs-lookup"><span data-stu-id="3e3d1-119">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="3e3d1-120">バインドされたデータソースに基づいて列を自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-120">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="3e3d1-121">方法: Windows フォーム DataGridView コントロールから自動生成された列を削除する</span><span class="sxs-lookup"><span data-stu-id="3e3d1-121">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="3e3d1-122">バインドされたデータソースから自動的に生成された列を非表示または削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-122">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="3e3d1-123">方法: Windows フォーム DataGridView コントロールの列の順序を変更する</span><span class="sxs-lookup"><span data-stu-id="3e3d1-123">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-124">バインドされたデータソースから自動的に生成される列を再配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-124">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="3e3d1-125">方法: データバインドされた Windows フォーム DataGridView コントロールに非バインド列を追加する</span><span class="sxs-lookup"><span data-stu-id="3e3d1-125">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="3e3d1-126">バインドされていない列を追加して、バインドされたデータソースからデータを補う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-126">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="3e3d1-127">方法 : オブジェクトを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="3e3d1-127">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="3e3d1-128">コントロールを任意のオブジェクトのコレクションにバインドして、各オブジェクトがそれぞれの行に表示されるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-128">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="3e3d1-129">方法 : Windows フォームの DataGridView 行にバインドされたオブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3e3d1-129">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="3e3d1-130">コントロールの特定の行にバインドされたオブジェクトを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-130">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="3e3d1-131">チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームの作成</span><span class="sxs-lookup"><span data-stu-id="3e3d1-131">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="3e3d1-132">1つのコントロールに表示される値が、別のコントロール `DataGridView` で現在選択されている行に依存するように、関連する2つのデータベーステーブルのデータを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-132">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="3e3d1-133">方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="3e3d1-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-134">イベントを処理して、 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> セルの値に応じてセルの外観を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-134">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3e3d1-135">リファレンス</span><span class="sxs-lookup"><span data-stu-id="3e3d1-135">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="3e3d1-136"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="3e3d1-137">プロパティに関するリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.DataSource%2A> します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-137">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="3e3d1-138"><xref:System.Windows.Forms.BindingSource> コンポーネントのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-138">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3e3d1-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e3d1-139">Related Sections</span></span>  
 [<span data-ttu-id="3e3d1-140">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="3e3d1-140">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e3d1-141">コントロールのデータに対してユーザーが実行できる追加および修正の仕方を変更する方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="3e3d1-141">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3d1-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e3d1-142">See also</span></span>

- [<span data-ttu-id="3e3d1-143">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="3e3d1-143">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="3e3d1-144">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="3e3d1-144">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
