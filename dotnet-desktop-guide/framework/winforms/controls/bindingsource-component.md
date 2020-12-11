---
title: BindingSource コンポーネント
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975114"
---
# <a name="bindingsource-component"></a><span data-ttu-id="a981e-102">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a981e-102">BindingSource Component</span></span>
<span data-ttu-id="a981e-103">コントロールにバインドするためにデータ ソースをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="a981e-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="a981e-104"><xref:System.Windows.Forms.BindingSource> コンポーネントは 2 つの目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a981e-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="a981e-105">1 つ目は、フォームのコントロールをデータにバインドするときに、間接レイヤーの役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="a981e-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="a981e-106"><xref:System.Windows.Forms.BindingSource> コンポーネントをデータ ソースにバインドして、フォームのコントロールを <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドすることで、これを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a981e-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="a981e-107">データとのそれ以上の対話 (移動、並べ替え、フィルタ処理、更新など) はすべて、<xref:System.Windows.Forms.BindingSource> コンポーネントを呼び出すことによって実行します。</span><span class="sxs-lookup"><span data-stu-id="a981e-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="a981e-108">2 つ目は、<xref:System.Windows.Forms.BindingSource> コンポーネントが、厳密に型指定されたデータ ソースとして機能することができます。</span><span class="sxs-lookup"><span data-stu-id="a981e-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="a981e-109"><xref:System.Windows.Forms.BindingSource.Add%2A> メソッドを持つ <xref:System.Windows.Forms.BindingSource> コンポーネントに型を追加すると、その型の一覧が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a981e-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a981e-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a981e-110">In This Section</span></span>  
 [<span data-ttu-id="a981e-111">BindingSource コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="a981e-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="a981e-112"><xref:System.Windows.Forms.BindingSource> コンポーネントの一般的な概念を導入し、データ ソースをコントロールにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="a981e-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="a981e-113">方法: Windows フォーム コントロールを DBNull データベース値にバインドする</span><span class="sxs-lookup"><span data-stu-id="a981e-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="a981e-114"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、<xref:System.DBNull> の値をデータ ソースから処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a981e-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="a981e-115">方法: Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a981e-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="a981e-116"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、表示されるデータに並べ替えとフィルター処理を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="a981e-117">方法: Windows フォーム BindingSource を使用して Web サービスにバインドする</span><span class="sxs-lookup"><span data-stu-id="a981e-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="a981e-118"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、Web サービスにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="a981e-119">方法: データ バインドで発生するエラーと例外を処理する</span><span class="sxs-lookup"><span data-stu-id="a981e-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="a981e-120"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、データ バインド操作で発生するエラーを適切に処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="a981e-121">方法: Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="a981e-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="a981e-122"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、型にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="a981e-123">方法: Windows フォーム コントロールをファクトリ オブジェクトにバインドする</span><span class="sxs-lookup"><span data-stu-id="a981e-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="a981e-124"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、ファクトリ オブジェクトやメソッドにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="a981e-125">方法: Windows フォーム BindingSource を使用して項目の追加をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a981e-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="a981e-126"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、新しい項目を作成し、データ ソースに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="a981e-127">方法: BindingSource ResetItem メソッドを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="a981e-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="a981e-128"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、変更通知をサポートしないデータ ソースに対して変更通知イベントを発生させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="a981e-129">方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="a981e-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="a981e-130"><xref:System.Windows.Forms.BindingSource> コントロールを使用して <xref:System.ComponentModel.INotifyPropertyChanged> から継承する型を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="a981e-131">方法: BindingSource を使用して Windows フォーム コントロール内にデータ ソースの更新を反映させる</span><span class="sxs-lookup"><span data-stu-id="a981e-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="a981e-132"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、データ ソースの変更に応答する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="a981e-133">方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する</span><span class="sxs-lookup"><span data-stu-id="a981e-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="a981e-134"><xref:System.Windows.Forms.BindingSource> を使用して、同じデータ ソースに複数のフォームをバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a981e-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a981e-135">リファレンス</span><span class="sxs-lookup"><span data-stu-id="a981e-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="a981e-136"><xref:System.Windows.Forms.BindingSource> コンポーネントのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="a981e-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="a981e-137"><xref:System.Windows.Forms.BindingNavigator> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="a981e-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a981e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a981e-138">Related Sections</span></span>  
 [<span data-ttu-id="a981e-139">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="a981e-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="a981e-140">Windows フォームのデータ バインディング アーキテクチャについて説明するトピックへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a981e-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="a981e-141">「[Visual Studio でのデータへのコントロールのバインド](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="a981e-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
