---
title: デザイナーを使用した DataGrid コントロールでの Master-Details リストの作成
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: a60cecf4c4344ab5aca18f76a59223c02d58a062
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974258"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="8373d-102">方法: デザイナーで Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="8373d-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="8373d-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="8373d-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="8373d-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8373d-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="8373d-105">に <xref:System.Data.DataSet> 一連の関連テーブルが含まれている場合は、2つのコントロールを使用して <xref:System.Windows.Forms.DataGrid> 、マスター/詳細形式でデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8373d-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="8373d-106">1つ <xref:System.Windows.Forms.DataGrid> はマスターグリッドとして指定され、2番目は詳細グリッドとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="8373d-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="8373d-107">マスターリストでエントリを選択すると、関連するすべての子エントリが詳細一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8373d-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="8373d-108">たとえば、に <xref:System.Data.DataSet> customers テーブルと関連する orders テーブルが含まれている場合は、customers テーブルをマスターグリッドに指定し、orders テーブルを詳細グリッドとして指定します。</span><span class="sxs-lookup"><span data-stu-id="8373d-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="8373d-109">マスターグリッドから顧客を選択すると、Orders テーブル内のその顧客に関連付けられているすべての注文が詳細グリッドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8373d-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>

 <span data-ttu-id="8373d-110">次の手順では、 **Windows アプリケーション** プロジェクト **([**  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**) が必要です。</span><span class="sxs-lookup"><span data-stu-id="8373d-110">The following procedure requires a **Windows Application** project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="8373d-111">デザイナーでマスター/詳細リストを作成するには</span><span class="sxs-lookup"><span data-stu-id="8373d-111">To create a master-details list in the designer</span></span>

1. <span data-ttu-id="8373d-112"><xref:System.Windows.Forms.DataGrid>フォームに2つのコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="8373d-112">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="8373d-113">詳細については、「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8373d-113">For more information, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="8373d-114">Visual Studio 2005 では、 <xref:System.Windows.Forms.DataGrid> コントロールは既定では **ツールボックス** に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8373d-114">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="8373d-115">詳細については、「 [方法: ツールボックスに項目を追加](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8373d-115">For more information, see [How to: Add Items to the Toolbox](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8373d-116">次の手順は、デザイン時のデータバインディングに [ **データソース** ] ウィンドウを使用する Visual Studio 2005 には適用されません。</span><span class="sxs-lookup"><span data-stu-id="8373d-116">The following steps are not applicable to Visual Studio 2005, which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="8373d-117">詳細については、「 [Visual Studio でのデータへのコントロールのバインド](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) 」および「 [方法: Windows フォームアプリケーションに関連データを表示する](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8373d-117">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).</span></span>

2. <span data-ttu-id="8373d-118">**サーバーエクスプローラー** からフォームに2つ以上のテーブルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8373d-118">Drag two or more tables from **Server Explorer** to the form.</span></span>

3. <span data-ttu-id="8373d-119">[ **データ** ] メニューの [データ **セットの生成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8373d-119">From the **Data** menu, select **Generate DataSet**.</span></span>

4. <span data-ttu-id="8373d-120">XML デザイナーを使用して、テーブル間のリレーションシップを設定します。</span><span class="sxs-lookup"><span data-stu-id="8373d-120">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="8373d-121">詳細については、MSDN の「XML スキーマおよびデータセットで一対多のリレーションシップを作成する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8373d-121">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>

5. <span data-ttu-id="8373d-122">[**ファイル**] メニューの [**すべてを保存**] を選択して、リレーションシップを保存します。</span><span class="sxs-lookup"><span data-stu-id="8373d-122">Save the relationships by selecting **Save All** from the **File** menu.</span></span>

6. <span data-ttu-id="8373d-123">次のように、 <xref:System.Windows.Forms.DataGrid> マスターグリッドを指定するコントロールを構成します。</span><span class="sxs-lookup"><span data-stu-id="8373d-123">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>

    1. <span data-ttu-id="8373d-124">プロパティの <xref:System.Data.DataSet> ドロップダウンリストからを選択し <xref:System.Windows.Forms.DataGrid.DataSource%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="8373d-124">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>

    2. <span data-ttu-id="8373d-125">プロパティのドロップダウンリストからマスターテーブル (たとえば、"Customers") を選択し <xref:System.Windows.Forms.DataGrid.DataMember%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="8373d-125">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>

7. <span data-ttu-id="8373d-126"><xref:System.Windows.Forms.DataGrid>詳細グリッドを指定するコントロールを次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="8373d-126">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>

    1. <span data-ttu-id="8373d-127">プロパティの <xref:System.Data.DataSet> ドロップダウンリストからを選択し <xref:System.Windows.Forms.DataGrid.DataSource%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="8373d-127">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>

    2. <span data-ttu-id="8373d-128">プロパティのドロップダウンリストから、マスターテーブルと詳細テーブルの間のリレーションシップ (例: "CustOrd") を選択し <xref:System.Windows.Forms.DataGrid.DataMember%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="8373d-128">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="8373d-129">リレーションシップを表示するには、 **+** ドロップダウンリストでマスターテーブルの横にあるプラス記号 () をクリックして、ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="8373d-129">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="8373d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="8373d-130">See also</span></span>

- [<span data-ttu-id="8373d-131">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="8373d-131">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="8373d-132">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="8373d-132">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="8373d-133">方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="8373d-133">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [<span data-ttu-id="8373d-134">Visual Studio でのデータへのコントロールのバインド</span><span class="sxs-lookup"><span data-stu-id="8373d-134">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
