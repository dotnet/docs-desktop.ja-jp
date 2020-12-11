---
title: ComboBox または ListBox コントロールをデータにバインドする
description: Windows フォーム ComboBox と ListBox をデータにバインドして、データベース内のデータの参照、新しいデータの入力、既存のデータの編集などのタスクを実行する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980956"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="ef9ab-103">方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする</span><span class="sxs-lookup"><span data-stu-id="ef9ab-103">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="ef9ab-104"><xref:System.Windows.Forms.ComboBox>とをデータにバインドすると、 <xref:System.Windows.Forms.ListBox> データベース内のデータの参照、新しいデータの入力、既存のデータの編集などのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-104">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="ef9ab-105">ComboBox または ListBox コントロールをバインドするには</span><span class="sxs-lookup"><span data-stu-id="ef9ab-105">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="ef9ab-106">プロパティを `DataSource` データソースオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-106">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="ef9ab-107">使用できるデータソースには、 <xref:System.Windows.Forms.BindingSource> データへのバインド、データテーブル、データビュー、データセット、データビューマネージャー、配列、またはインターフェイスを実装する任意のクラスが含ま <xref:System.Collections.IList> れます。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-107">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="ef9ab-108">詳細については、「 [Windows フォームでサポートされるデータソース](../data-sources-supported-by-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-108">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="ef9ab-109">テーブルにバインドする場合は、 `DisplayMember` プロパティをデータソース内の列の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-109">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="ef9ab-110">\- または</span><span class="sxs-lookup"><span data-stu-id="ef9ab-110">\- or -</span></span>  
  
     <span data-ttu-id="ef9ab-111">にバインドする場合は <xref:System.Collections.IList> 、表示メンバーをリスト内の型のパブリックプロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-111">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="ef9ab-112">など、インターフェイスを実装していないデータソースにバインドされている場合、 <xref:System.ComponentModel.IBindingList> <xref:System.Collections.ArrayList> データソースの更新時にバインドされたコントロールのデータは更新されません。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-112">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="ef9ab-113">たとえば、にバインドされたコンボボックスがあり、にデータが追加されている場合、 <xref:System.Collections.ArrayList> <xref:System.Collections.ArrayList> これらの新しい項目はコンボボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-113">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="ef9ab-114">ただし、 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> コントロールがバインドされているクラスのインスタンスでメソッドとメソッドを呼び出すことにより、コンボボックスを強制的に更新でき <xref:System.Windows.Forms.BindingContext> ます。</span><span class="sxs-lookup"><span data-stu-id="ef9ab-114">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9ab-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef9ab-115">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="ef9ab-116">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="ef9ab-116">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="ef9ab-117">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="ef9ab-117">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="ef9ab-118">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="ef9ab-118">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
