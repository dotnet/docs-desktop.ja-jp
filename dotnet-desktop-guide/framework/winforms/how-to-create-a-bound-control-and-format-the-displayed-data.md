---
title: '方法: バインド コントロールを作成して表示データの書式を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: e1448e0dcb80a7ac7ab0199b14957bddec27c133
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974360"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="4c479-102">方法: バインド コントロールを作成して表示データの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="4c479-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="4c479-103">Windows フォームデータバインディングでは、[ **書式設定と詳細バインド** ] ダイアログボックスを使用して、データバインドコントロールに表示されるデータの書式を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4c479-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>

## <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="4c479-104">コントロールをバインドして表示データの書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="4c479-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="4c479-105">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="4c479-105">Connect to a data source.</span></span> <span data-ttu-id="4c479-106">詳細については、「 [データソースへの接続](/dotnet/framework/data/adonet/connecting-to-a-data-source)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c479-106">For more information, see [Connecting to a Data Source](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span></span>

2. <span data-ttu-id="4c479-107">Visual Studio でフォーム上のコントロールを選択し、[ **プロパティ** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4c479-107">In Visual Studio, select the control on the form, and then open the **Properties** window.</span></span>

3. <span data-ttu-id="4c479-108">[ **(連結)** ] プロパティを展開し、[ **(詳細)** ] ボックスで、省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン ([...]) をクリックして ](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png) 、[ **書式設定と詳細バインド** ] ダイアログボックスを表示します。このダイアログボックスには、そのコントロールのプロパティの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c479-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="4c479-109">バインドするプロパティを選択し、[ **バインド** ] 矢印を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c479-109">Select the property you want to bind, and then select the **Binding** arrow.</span></span>

     <span data-ttu-id="4c479-110">使用できるデータ ソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c479-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="4c479-111">目的の 1 つのデータ要素が見つかるまで、バインド先のデータ ソースを展開します。</span><span class="sxs-lookup"><span data-stu-id="4c479-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="4c479-112">たとえば、データセットのテーブル内の列の値にバインドする場合は、データセットの名前を展開し、次にテーブル名を展開して、列名を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c479-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="4c479-113">バインド先の要素の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c479-113">Select the name of an element to bind to.</span></span>

7. <span data-ttu-id="4c479-114">[ **形式の種類** ] ボックスで、コントロールに表示されるデータに適用する形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c479-114">In the **Format type** box, select the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="4c479-115">どの形式でも、データ ソースに <xref:System.DBNull> が含まれている場合には、コントロールに表示する値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c479-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="4c479-116">それ以外の場合、オプションは、選択する形式の種類に応じて多少変わります。</span><span class="sxs-lookup"><span data-stu-id="4c479-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="4c479-117">次の表に、形式の種類とオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="4c479-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="4c479-118">形式の種類</span><span class="sxs-lookup"><span data-stu-id="4c479-118">Format type</span></span>|<span data-ttu-id="4c479-119">書式設定のオプション</span><span class="sxs-lookup"><span data-stu-id="4c479-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="4c479-120">書式設定なし</span><span class="sxs-lookup"><span data-stu-id="4c479-120">No Formatting</span></span>|<span data-ttu-id="4c479-121">オプションなし。</span><span class="sxs-lookup"><span data-stu-id="4c479-121">No options.</span></span>|
    |<span data-ttu-id="4c479-122">数値</span><span class="sxs-lookup"><span data-stu-id="4c479-122">Numeric</span></span>|<span data-ttu-id="4c479-123">小数点 **以下** の桁数をアップダウンコントロールで指定します。</span><span class="sxs-lookup"><span data-stu-id="4c479-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="4c479-124">通貨</span><span class="sxs-lookup"><span data-stu-id="4c479-124">Currency</span></span>|<span data-ttu-id="4c479-125">小数点 **以下** の桁数をアップダウンコントロールで指定します。</span><span class="sxs-lookup"><span data-stu-id="4c479-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="4c479-126">Date Time</span><span class="sxs-lookup"><span data-stu-id="4c479-126">Date Time</span></span>|<span data-ttu-id="4c479-127">[ **種類** の選択] ボックスでいずれかの項目を選択して、日付と時刻を表示する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c479-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="4c479-128">[指数]</span><span class="sxs-lookup"><span data-stu-id="4c479-128">Scientific</span></span>|<span data-ttu-id="4c479-129">小数点 **以下** の桁数をアップダウンコントロールで指定します。</span><span class="sxs-lookup"><span data-stu-id="4c479-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="4c479-130">カスタム</span><span class="sxs-lookup"><span data-stu-id="4c479-130">Custom</span></span>|<span data-ttu-id="4c479-131">カスタム書式指定文字列を使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="4c479-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="4c479-132">詳細については、[型の書式設定](/dotnet/standard/base-types/formatting-types)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c479-132">For more information, see [Formatting Types](/dotnet/standard/base-types/formatting-types).</span></span> <span data-ttu-id="4c479-133">**注:**  カスタム書式指定文字列は、データソースとバインドされたコントロールの間で正常にラウンドトリップすることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="4c479-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="4c479-134">その代わりに、バインディングで <xref:System.Windows.Forms.Binding.Parse> イベントまたは <xref:System.Windows.Forms.Binding.Format> イベントを処理し、イベント処理コードでカスタム書式を適用します。</span><span class="sxs-lookup"><span data-stu-id="4c479-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="4c479-135">[ **OK** ] を選択して [ **書式設定と詳細バインド** ] ダイアログボックスを閉じ、プロパティウィンドウに戻ります。</span><span class="sxs-lookup"><span data-stu-id="4c479-135">Select **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c479-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c479-136">See also</span></span>

- [<span data-ttu-id="4c479-137">方法: Windows フォームに単純バインド コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="4c479-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="4c479-138">Windows フォームでのユーザー入力の検証</span><span class="sxs-lookup"><span data-stu-id="4c479-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="4c479-139">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="4c479-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
