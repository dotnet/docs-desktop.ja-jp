---
title: DomainUpDown コントロールにプログラムで項目を追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982019"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="4e744-102">方法 : Windows フォーム DomainUpDown コントロールにプログラムで項目を追加する</span><span class="sxs-lookup"><span data-stu-id="4e744-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="4e744-103">コード内の Windows フォームコントロールに項目を追加でき <xref:System.Windows.Forms.DomainUpDown> ます。</span><span class="sxs-lookup"><span data-stu-id="4e744-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="4e744-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>クラスのメソッドまたはメソッドを呼び出して <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 、コントロールのプロパティに項目を追加し <xref:System.Windows.Forms.DomainUpDown.Items%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4e744-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="4e744-105">メソッドは、 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> コレクションの末尾に項目を追加し <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> ます。メソッドは、指定した位置に項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="4e744-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="4e744-106">新しい項目を追加するには</span><span class="sxs-lookup"><span data-stu-id="4e744-106">To add a new item</span></span>  
  
1. <span data-ttu-id="4e744-107">項目 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> の一覧の末尾に項目を追加するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e744-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="4e744-108">または</span><span class="sxs-lookup"><span data-stu-id="4e744-108">-or-</span></span>  
  
2. <span data-ttu-id="4e744-109"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>リスト内の指定した位置に項目を挿入するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e744-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4e744-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e744-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4e744-111">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="4e744-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="4e744-112">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4e744-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
