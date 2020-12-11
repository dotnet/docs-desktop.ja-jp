---
title: ComboBox、ListBox、または CheckedListBox コントロールのルックアップテーブルを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 57dc95fc16d77ee1492f53bf57eac001a343ca8f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974264"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="ae97b-102">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成する</span><span class="sxs-lookup"><span data-stu-id="ae97b-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>

<span data-ttu-id="ae97b-103">Windows フォーム上ではわかりやすい形式でデータを表示し、一方プログラムにはより意味のある形式でデータを格納すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae97b-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="ae97b-104">たとえば、食品の注文書の場合、リスト ボックスにメニュー項目が名前で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="ae97b-105">一方、注文を記録するデータ テーブルには、食品を表す一意の ID 番号が含まれることになります。</span><span class="sxs-lookup"><span data-stu-id="ae97b-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="ae97b-106">次の表は、食品の注文書データを格納および表示する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae97b-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="ae97b-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="ae97b-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="ae97b-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="ae97b-108">OrderID</span></span>|<span data-ttu-id="ae97b-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="ae97b-109">ItemID</span></span>|<span data-ttu-id="ae97b-110">Quantity</span><span class="sxs-lookup"><span data-stu-id="ae97b-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="ae97b-111">4085</span><span class="sxs-lookup"><span data-stu-id="ae97b-111">4085</span></span>|<span data-ttu-id="ae97b-112">12</span><span class="sxs-lookup"><span data-stu-id="ae97b-112">12</span></span>|<span data-ttu-id="ae97b-113">1</span><span class="sxs-lookup"><span data-stu-id="ae97b-113">1</span></span>|  
|<span data-ttu-id="ae97b-114">4086</span><span class="sxs-lookup"><span data-stu-id="ae97b-114">4086</span></span>|<span data-ttu-id="ae97b-115">13</span><span class="sxs-lookup"><span data-stu-id="ae97b-115">13</span></span>|<span data-ttu-id="ae97b-116">3</span><span class="sxs-lookup"><span data-stu-id="ae97b-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="ae97b-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="ae97b-117">ItemTable</span></span>  
  
|<span data-ttu-id="ae97b-118">ID</span><span class="sxs-lookup"><span data-stu-id="ae97b-118">ID</span></span>|<span data-ttu-id="ae97b-119">名前</span><span class="sxs-lookup"><span data-stu-id="ae97b-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="ae97b-120">12</span><span class="sxs-lookup"><span data-stu-id="ae97b-120">12</span></span>|<span data-ttu-id="ae97b-121">ポテト</span><span class="sxs-lookup"><span data-stu-id="ae97b-121">Potato</span></span>|  
|<span data-ttu-id="ae97b-122">13</span><span class="sxs-lookup"><span data-stu-id="ae97b-122">13</span></span>|<span data-ttu-id="ae97b-123">チキン</span><span class="sxs-lookup"><span data-stu-id="ae97b-123">Chicken</span></span>|  
  
 <span data-ttu-id="ae97b-124">このシナリオでは、1つのテーブル **OrderDetailsTable** に、表示と保存に関係する実際の情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="ae97b-125">しかし、スペースを節約するために、これはかなり謎めいた方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="ae97b-126">もう1つの **Itemtable** というテーブルには、どの ID 番号がどの食品名に相当するかに関する外観関連の情報だけが含まれており、実際の食品注文については何もありません。</span><span class="sxs-lookup"><span data-stu-id="ae97b-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="ae97b-127">**Itemtable** は <xref:System.Windows.Forms.ComboBox> 、3つのプロパティを介して、、またはコントロールに接続され <xref:System.Windows.Forms.ListBox> <xref:System.Windows.Forms.CheckedListBox> ます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="ae97b-128">プロパティには `DataSource` 、このテーブルの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="ae97b-129">プロパティには、 `DisplayMember` コントロールに表示する、そのテーブルのデータ列が含まれます (食品名)。</span><span class="sxs-lookup"><span data-stu-id="ae97b-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="ae97b-130">プロパティには、 `ValueMember` 格納されている情報 (ID 番号) を含むテーブルのデータ列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="ae97b-131">**OrderDetailsTable** は、プロパティを通じてアクセスされるバインドコレクションによってコントロールに接続され <xref:System.Windows.Forms.Control.DataBindings%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="ae97b-132">バインドオブジェクトをコレクションに追加する場合は、データソース ( **OrderDetailsTable**) の特定のデータメンバー (ID 番号の列) にコントロールプロパティを接続します。</span><span class="sxs-lookup"><span data-stu-id="ae97b-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="ae97b-133">コントロールで選択がなされる際、このテーブルはフォーム入力が保存される場所です。</span><span class="sxs-lookup"><span data-stu-id="ae97b-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="ae97b-134">ルックアップ テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="ae97b-134">To create a lookup table</span></span>  
  
1. <span data-ttu-id="ae97b-135">フォームに <xref:System.Windows.Forms.ComboBox>、<xref:System.Windows.Forms.ListBox>、または <xref:System.Windows.Forms.CheckedListBox> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae97b-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2. <span data-ttu-id="ae97b-136">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="ae97b-136">Connect to your data source.</span></span>  
  
3. <span data-ttu-id="ae97b-137">2 つのテーブル間のデータ リレーションシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="ae97b-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="ae97b-138">「 [DataRelation オブジェクトの概要」を](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae97b-138">See [Introduction to DataRelation Objects](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4. <span data-ttu-id="ae97b-139">次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae97b-139">Set the following properties.</span></span> <span data-ttu-id="ae97b-140">これらはコードまたはデザイナーで設定できます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="ae97b-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae97b-141">Property</span></span>|<span data-ttu-id="ae97b-142">設定</span><span class="sxs-lookup"><span data-stu-id="ae97b-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="ae97b-143">どの ID 番号がどの項目に相当するかについての情報を含むテーブル。</span><span class="sxs-lookup"><span data-stu-id="ae97b-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="ae97b-144">前のシナリオでは、これは `ItemTable` です。</span><span class="sxs-lookup"><span data-stu-id="ae97b-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="ae97b-145">コントロールに表示するデータ ソース テーブルの列。</span><span class="sxs-lookup"><span data-stu-id="ae97b-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="ae97b-146">前のシナリオでは、これはです `"Name"` (コードで設定するには、引用符を使用します)。</span><span class="sxs-lookup"><span data-stu-id="ae97b-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="ae97b-147">格納された情報を含むデータ ソース テーブルの列。</span><span class="sxs-lookup"><span data-stu-id="ae97b-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="ae97b-148">前のシナリオでは、これはです `"ID"` (コードで設定するには、引用符を使用します)。</span><span class="sxs-lookup"><span data-stu-id="ae97b-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5. <span data-ttu-id="ae97b-149">プロシージャで <xref:System.Windows.Forms.ControlBindingsCollection> クラスの <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> メソッドを呼び出して、フォーム入力を記録するテーブルにコントロールの <xref:System.Windows.Forms.ListControl.SelectedValue%2A> プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="ae97b-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="ae97b-150">また <xref:System.Windows.Forms.Control.DataBindings%2A> 、[ **プロパティ** ] ウィンドウでコントロールのプロパティにアクセスすることにより、コードではなくデザイナーでこの操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="ae97b-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="ae97b-151">前のシナリオでは、これはで `OrderDetailsTable` あり、列は `"ItemID"` です。</span><span class="sxs-lookup"><span data-stu-id="ae97b-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ae97b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae97b-152">See also</span></span>

- [<span data-ttu-id="ae97b-153">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="ae97b-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="ae97b-154">ListBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ae97b-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="ae97b-155">ComboBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ae97b-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="ae97b-156">CheckedListBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ae97b-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="ae97b-157">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="ae97b-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
