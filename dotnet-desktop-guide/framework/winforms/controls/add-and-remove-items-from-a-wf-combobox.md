---
title: ComboBox、ListBox、または CheckedListBox コントロールの項目を追加および削除する
ms.date: 03/30/2017
description: Windows フォーム ComboBox、ListBox、CheckedListBox の各コントロールを、データバインディングなしで簡単に追加および削除する方法について説明します。
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: f3701257bbe410bf03c4c21700705e87b581bf2e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981124"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="a6a0b-103">方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a6a0b-103">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="a6a0b-104">項目は、さまざまな方法で Windows フォームコンボボックス、リストボックス、またはチェックリストボックスに追加できます。これらのコントロールはさまざまなデータソースにバインドできるためです。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-104">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="a6a0b-105">ただし、このトピックでは、最も簡単な方法について説明し、データバインディングは不要です。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-105">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="a6a0b-106">通常、表示される項目は文字列です。ただし、任意のオブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-106">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="a6a0b-107">コントロールに表示されるテキストは、オブジェクトのメソッドによって返される値です `ToString` 。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-107">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="a6a0b-108">項目を追加するには</span><span class="sxs-lookup"><span data-stu-id="a6a0b-108">To add items</span></span>  
  
1. <span data-ttu-id="a6a0b-109">クラスのメソッドを使用して、文字列またはオブジェクトをリストに追加し `Add` `ObjectCollection` ます。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-109">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="a6a0b-110">コレクションは、次のプロパティを使用して参照され `Items` ます。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-110">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="a6a0b-111">または</span><span class="sxs-lookup"><span data-stu-id="a6a0b-111">or -</span></span>  
  
2. <span data-ttu-id="a6a0b-112">メソッドを使用して、リスト内の目的の位置に文字列またはオブジェクトを挿入し `Insert` ます。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-112">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="a6a0b-113">または</span><span class="sxs-lookup"><span data-stu-id="a6a0b-113">or -</span></span>  
  
3. <span data-ttu-id="a6a0b-114">配列全体をコレクションに割り当て `Items` ます。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-114">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="a6a0b-115">アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="a6a0b-115">To remove an item</span></span>  
  
1. <span data-ttu-id="a6a0b-116">`Remove` `RemoveAt` 項目を削除するには、メソッドまたはメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-116">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="a6a0b-117">`Remove` には、削除する項目を指定する引数が1つあります。`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="a6a0b-117">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="a6a0b-118">指定したインデックス番号の項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-118">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="a6a0b-119">すべての項目を削除するには</span><span class="sxs-lookup"><span data-stu-id="a6a0b-119">To remove all items</span></span>  
  
1. <span data-ttu-id="a6a0b-120">メソッドを呼び出して `Clear` 、コレクションからすべての項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="a6a0b-120">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a6a0b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6a0b-121">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="a6a0b-122">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える</span><span class="sxs-lookup"><span data-stu-id="a6a0b-122">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="a6a0b-123">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a6a0b-123">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="a6a0b-124">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="a6a0b-124">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
