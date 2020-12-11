---
title: DomainUpDown コントロールからの項目の削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974762"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="23dc0-102">方法: Windows フォームの DomainUpDown コントロールから項目を削除する</span><span class="sxs-lookup"><span data-stu-id="23dc0-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="23dc0-103"><xref:System.Windows.Forms.DomainUpDown> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> クラスのメソッドまたはメソッドを呼び出すことによって、Windows フォームコントロールから項目を削除でき <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="23dc0-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="23dc0-104">メソッドは特定の項目を削除しますが、 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> メソッドはその位置によって項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="23dc0-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="23dc0-105">アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="23dc0-105">To remove an item</span></span>  
  
- <span data-ttu-id="23dc0-106"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>クラスのメソッドを使用し <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> て、名前を指定して項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="23dc0-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="23dc0-107">または</span><span class="sxs-lookup"><span data-stu-id="23dc0-107">-or-</span></span>  
  
- <span data-ttu-id="23dc0-108"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>位置によって項目を削除するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="23dc0-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23dc0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="23dc0-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="23dc0-110">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="23dc0-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="23dc0-111">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="23dc0-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
