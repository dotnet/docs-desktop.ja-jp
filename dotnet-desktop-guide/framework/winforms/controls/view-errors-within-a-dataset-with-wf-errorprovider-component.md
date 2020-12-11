---
title: ErrorProvider コンポーネントを使用してデータセット内のエラーを表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 8c2155bf288db89b5d53567738fd399b915d50b6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983924"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="49e9c-102">方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内にエラーを表示する</span><span class="sxs-lookup"><span data-stu-id="49e9c-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="49e9c-103">Windows フォームコンポーネントを使用すると、データ <xref:System.Windows.Forms.ErrorProvider> セットまたはその他のデータソース内の列のエラーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="49e9c-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="49e9c-104">コンポーネントが <xref:System.Windows.Forms.ErrorProvider> フォームにデータエラーを表示するには、コントロールに直接関連付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49e9c-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="49e9c-105">データソースにバインドされると、同じデータソースにバインドされているコントロールの横にエラーアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49e9c-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49e9c-106">実行時にエラープロバイダーのプロパティとプロパティを変更した場合は、メソッドを使用して <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> 競合を回避する必要があり <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="49e9c-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="49e9c-107">データエラーを表示するには</span><span class="sxs-lookup"><span data-stu-id="49e9c-107">To display data errors</span></span>  
  
1. <span data-ttu-id="49e9c-108">コンポーネントをデータテーブル内の特定の列にバインドします。</span><span class="sxs-lookup"><span data-stu-id="49e9c-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2. <span data-ttu-id="49e9c-109"><xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>プロパティをフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="49e9c-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. <span data-ttu-id="49e9c-110">現在のレコードの位置を、列エラーを含む行に設定します。</span><span class="sxs-lookup"><span data-stu-id="49e9c-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="49e9c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="49e9c-111">See also</span></span>

- [<span data-ttu-id="49e9c-112">ErrorProvider コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="49e9c-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="49e9c-113">方法: Windows フォーム ErrorProvider コンポーネントを使用してフォーム妥当性検査でエラー アイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="49e9c-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)
