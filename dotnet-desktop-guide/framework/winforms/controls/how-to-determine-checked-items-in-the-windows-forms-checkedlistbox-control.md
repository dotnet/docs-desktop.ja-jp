---
title: CheckedListBox コントロールでチェックされている項目を確認する
description: CheckedItems プロパティに格納されているコレクションを反復処理して、Windows フォーム CheckedListBox コントロールでチェックされている項目を確認する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: fd8845ef83da7406ff4f1468506a23e3f4d386a0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982143"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="7e9a9-103">方法: Windows フォーム CheckedListBox コントロールでオンになっている項目を判断する</span><span class="sxs-lookup"><span data-stu-id="7e9a9-103">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="7e9a9-104">Windows フォームコントロールにデータを表示する場合は、 <xref:System.Windows.Forms.CheckedListBox> プロパティに格納されているコレクションを反復処理するか、 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> メソッドを使用してリストをステップ実行し、 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> どの項目がチェックされるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-104">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="7e9a9-105">メソッドは、 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 引数として項目のインデックス番号を取得し、 `true` またはを返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-105">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="7e9a9-106">期待しているものとは異なり、 <xref:System.Windows.Forms.ListBox.SelectedItems%2A> プロパティとプロパティではどの <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> 項目がチェックされるかが決定されないため、どの項目が強調表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-106">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="7e9a9-107">CheckedListBox コントロールでチェックされている項目を確認するには</span><span class="sxs-lookup"><span data-stu-id="7e9a9-107">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="7e9a9-108">コレクションが0から始まる <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> ため、コレクションを反復処理して0から開始します。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-108">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="7e9a9-109">このメソッドは、リスト全体ではなく、チェックされた項目の一覧に項目番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-109">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="7e9a9-110">このため、リストの最初の項目がチェックされず、2番目の項目がオンになっている場合は、次のコードに "Checked Item 1 = MyListItem2" のようなテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-110">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - <span data-ttu-id="7e9a9-111">または</span><span class="sxs-lookup"><span data-stu-id="7e9a9-111">or -</span></span>  
  
2. <span data-ttu-id="7e9a9-112">コレクションをステップ実行します。コレクションは0から始まり、 <xref:System.Windows.Forms.CheckedListBox.Items%2A> <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 各項目に対してメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-112">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="7e9a9-113">この方法では、一覧の項目番号が表示されるので、リスト内の最初の項目がチェックされず、2番目の項目がオンになっている場合は、"Item 2 = MyListItem2" のような内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e9a9-113">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7e9a9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e9a9-114">See also</span></span>

- [<span data-ttu-id="7e9a9-115">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="7e9a9-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
