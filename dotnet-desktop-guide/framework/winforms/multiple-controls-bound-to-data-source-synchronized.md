---
title: '方法: 複数のコントロールを 1 つのデータ ソースにバインドして同期状態を保つ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8a39c50bfc452c807a18a9bf0a65e56cb75d20aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974340"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="4c19a-102">方法: 複数のコントロールを 1 つのデータ ソースにバインドして同期状態を保つ</span><span class="sxs-lookup"><span data-stu-id="4c19a-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="4c19a-103">Windows フォームでデータバインディングを使用する場合、複数のコントロールが同じデータソースにバインドされることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="4c19a-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="4c19a-104">場合によっては、コントロールのバインドされたプロパティが相互に同期していることを確認するために、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c19a-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="4c19a-105">これらの手順は、次の2つの状況で必要になります。</span><span class="sxs-lookup"><span data-stu-id="4c19a-105">These steps are necessary in two situations:</span></span>  
  
- <span data-ttu-id="4c19a-106">データソースが <xref:System.ComponentModel.IBindingList> を実装しておらず、 <xref:System.ComponentModel.IBindingList.ListChanged> 型のイベントを生成する場合は <xref:System.ComponentModel.ListChangedType.ItemChanged> 。</span><span class="sxs-lookup"><span data-stu-id="4c19a-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
- <span data-ttu-id="4c19a-107">データソースがを実装している場合は <xref:System.ComponentModel.IEditableObject> 。</span><span class="sxs-lookup"><span data-stu-id="4c19a-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="4c19a-108">前者の場合は、を使用して、 <xref:System.Windows.Forms.BindingSource> データソースをコントロールにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="4c19a-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="4c19a-109">後者の場合、を使用して <xref:System.Windows.Forms.BindingSource> イベントを処理 <xref:System.Windows.Forms.BindingSource.BindingComplete> し、 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> 関連付けられているでを呼び出し <xref:System.Windows.Forms.BindingManagerBase> ます。</span><span class="sxs-lookup"><span data-stu-id="4c19a-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c19a-110">例</span><span class="sxs-lookup"><span data-stu-id="4c19a-110">Example</span></span>  
 <span data-ttu-id="4c19a-111">次のコード例では、コンポーネントを使用して、3つのコントロール (2 つのテキストボックスコントロールと <xref:System.Windows.Forms.DataGridView> コントロール) を内の同じ列にバインドする方法を示し <xref:System.Data.DataSet> <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="4c19a-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="4c19a-112">この例では、イベントを処理し、 <xref:System.Windows.Forms.BindingSource.BindingComplete> 1 つのテキストボックスのテキスト値が変更されたときに、追加のテキストボックスと <xref:System.Windows.Forms.DataGridView> コントロールが正しい値で更新されるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4c19a-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="4c19a-113">この例では、を使用して、 <xref:System.Windows.Forms.BindingSource> データソースとコントロールをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4c19a-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="4c19a-114">または、コントロールを直接データソースにバインドし、 <xref:System.Windows.Forms.BindingManagerBase> フォームのからバインドのを取得して、のイベントを処理することもでき <xref:System.Windows.Forms.Control.BindingContext%2A> <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> <xref:System.Windows.Forms.BindingManagerBase> ます。</span><span class="sxs-lookup"><span data-stu-id="4c19a-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="4c19a-115">これを行う方法の例については、のイベントに関するヘルプページを参照してください <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> <xref:System.Windows.Forms.BindingManagerBase> 。</span><span class="sxs-lookup"><span data-stu-id="4c19a-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c19a-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4c19a-116">Compiling the Code</span></span>  
  
- <span data-ttu-id="4c19a-117">このコード例では、</span><span class="sxs-lookup"><span data-stu-id="4c19a-117">This code example requires</span></span>  
  
- <span data-ttu-id="4c19a-118"><xref:System>、<xref:System.Windows.Forms>、および <xref:System.Drawing> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="4c19a-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
- <span data-ttu-id="4c19a-119">イベントが処理されたフォーム <xref:System.Windows.Forms.Form.Load> と、 `InitializeControlsAndDataSource` フォームのイベントハンドラーからの例のメソッドの呼び出し <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="4c19a-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c19a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c19a-120">See also</span></span>

- [<span data-ttu-id="4c19a-121">方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する</span><span class="sxs-lookup"><span data-stu-id="4c19a-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [<span data-ttu-id="4c19a-122">Windows フォーム データ バインディングの変更通知</span><span class="sxs-lookup"><span data-stu-id="4c19a-122">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="4c19a-123">データ連結に関連するインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c19a-123">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)
- [<span data-ttu-id="4c19a-124">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="4c19a-124">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
