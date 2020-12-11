---
title: '方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: cd8c3fba87fd5ab9acf9159fc1130ee28ed38497
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983447"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="05d62-102">方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="05d62-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>

<span data-ttu-id="05d62-103">コンポーネントは、データソースに <xref:System.Windows.Forms.BindingSource> 含まれている型が <xref:System.ComponentModel.INotifyPropertyChanged> を実装し、プロパティ値が変更されたときにイベントを発生させるときに、データソースの変更を自動的に検出し <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="05d62-103">The <xref:System.Windows.Forms.BindingSource> component automatically detects changes in a data source when the type contained in the data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="05d62-104">この変更の検出は、にバインドされたコントロールが <xref:System.Windows.Forms.BindingSource> データソースの値の変更に応じて自動的に更新されるため便利です。</span><span class="sxs-lookup"><span data-stu-id="05d62-104">This change detection is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> automatically update as the data source values change.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05d62-105">データ ソースが <xref:System.ComponentModel.INotifyPropertyChanged> を実装し、非同期操作を実行している場合は、バック グラウンド スレッド上のデータ ソースを変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="05d62-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="05d62-106">代わりに、バック グラウンド スレッド上のデータを読み取り、UI スレッドでリストにデータをマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05d62-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05d62-107">例</span><span class="sxs-lookup"><span data-stu-id="05d62-107">Example</span></span>  

 <span data-ttu-id="05d62-108">次のコード例は、<xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスの簡単な実装を示します。</span><span class="sxs-lookup"><span data-stu-id="05d62-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="05d62-109"><xref:System.Windows.Forms.BindingSource> が <xref:System.ComponentModel.INotifyPropertyChanged> 型の一覧にバインドされるときに、<xref:System.Windows.Forms.BindingSource> がバインドされたコントロールにデータ ソースの変更を自動的に渡す方法も示します。</span><span class="sxs-lookup"><span data-stu-id="05d62-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="05d62-110">`CallerMemberName` 属性を使用する場合、`NotifyPropertyChanged` メソッドの呼び出しが、文字列引数としてプロパティ名を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="05d62-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="05d62-111">詳細については、「 [呼び出し元情報 (C#)](/dotnet/csharp/language-reference/attributes/caller-information) 」または「 [呼び出し元情報 (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/caller-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d62-111">For more information, see [Caller Information (C#)](/dotnet/csharp/language-reference/attributes/caller-information) or [Caller Information (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/caller-information).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="05d62-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="05d62-112">Compiling the Code</span></span>  

 <span data-ttu-id="05d62-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="05d62-113">This example requires:</span></span>  
  
- <span data-ttu-id="05d62-114">System、system.string、Drawing、および Windows の各アセンブリへの参照です。</span><span class="sxs-lookup"><span data-stu-id="05d62-114">References to the System, System.Data, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d62-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="05d62-115">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="05d62-116">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="05d62-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="05d62-117">方法: BindingSource ResetItem メソッドを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="05d62-117">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
