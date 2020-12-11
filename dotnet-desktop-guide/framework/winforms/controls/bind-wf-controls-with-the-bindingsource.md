---
title: デザイナーを使用してコントロールを BindingSource コンポーネントにバインドする
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: ec4e556e855a2c86dc280e1c386e9dabc2319c57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981087"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="ed1df-102">方法: デザイナーを使用して Windows フォーム コントロールを BindingSource コンポーネントにバインドする</span><span class="sxs-lookup"><span data-stu-id="ed1df-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>

<span data-ttu-id="ed1df-103">フォームにコントロールを追加し、アプリケーションのユーザーインターフェイスを決定したら、コントロールをデータソースにバインドできます。これにより、ユーザーがアプリケーションに関連するデータを変更したり保存したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ed1df-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="ed1df-104">Windows フォームでコントロールまたは一連のコントロールをバインドすることは、 <xref:System.Windows.Forms.BindingSource> フォーム上のコントロールとデータソースの間のブリッジとして、コントロールを使用すると最も簡単に実現できます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="ed1df-105">フォーム上の1つ以上のコントロールをデータにバインドできます。次の手順では、 <xref:System.Windows.Forms.TextBox> コントロールがデータソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="ed1df-106">この手順を完了するには、データベースから派生したデータソースにバインドすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ed1df-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="ed1df-107">他のデータストアからデータソースを作成する方法の詳細については、「 [新しいデータソースの追加](/visualstudio/data-tools/add-new-data-sources)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed1df-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="ed1df-108">デザイン時にコントロールをバインドするには</span><span class="sxs-lookup"><span data-stu-id="ed1df-108">To bind a control at design time</span></span>

1. <span data-ttu-id="ed1df-109">コントロールを <xref:System.Windows.Forms.TextBox> フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ed1df-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="ed1df-110">[ **プロパティ** ] ウィンドウで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ed1df-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="ed1df-111">[ **(連結)** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="ed1df-112">プロパティの横にある矢印をクリックし <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="ed1df-113">**DataSource** UI 型エディターが開きます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="ed1df-114">データソースが既にプロジェクトまたはフォーム用に構成されている場合は、そのデータソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="ed1df-115">**[プロジェクト データ ソースの追加]** をクリックしてデータに接続し、データ ソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="ed1df-116">**データ ソース構成ウィザード** の開始ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed1df-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="ed1df-117">[ **データソースの種類を選択** ] ページで、[ **データベース**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="ed1df-118">[ **データ接続の選択** ] ページで、使用可能な接続の一覧からデータ接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="ed1df-119">目的のデータ接続が使用できない場合は、[ **新しい接続** ] を選択して新しいデータ接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="ed1df-120">[ **はい、接続を保存** します] を選択して、アプリケーション構成ファイルに接続文字列を保存します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="ed1df-121">アプリケーションで使用するデータベース オブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="ed1df-122">この場合、を表示するテーブルのフィールドを選択し <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="ed1df-123">必要な場合は、既定のデータセット名を変更します。</span><span class="sxs-lookup"><span data-stu-id="ed1df-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="ed1df-124">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed1df-124">Click **Finish**.</span></span>

11. <span data-ttu-id="ed1df-125">[ **プロパティ** ] ウィンドウで、プロパティの横にある矢印を <xref:System.Windows.Forms.TextBox.Text%2A> もう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="ed1df-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="ed1df-126">**DataSource** UI 型エディターで、バインド先のフィールドの名前を選択し <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="ed1df-127">データ **ソース** UI 型エディターが閉じられ、データセットと、 <xref:System.Windows.Forms.BindingSource> そのデータ接続に固有のテーブルアダプターがフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ed1df-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed1df-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed1df-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="ed1df-129">新しいデータ ソースの追加</span><span class="sxs-lookup"><span data-stu-id="ed1df-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="ed1df-130">[データ ソース ウィンドウ](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ed1df-130">[Data Sources Window](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
