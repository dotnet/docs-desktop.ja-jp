---
title: ComboBox と ListBox
description: Windows フォーム ComboBox と Windows フォーム ListBox を使用する方法について説明します。また、タスクに適しているかどうかを判断する方法についても説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982676"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="e5935-103">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="e5935-103">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="e5935-104">とのコントロールには <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> 同様の動作があり、場合によっては交換可能である場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e5935-104">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="e5935-105">ただし、タスクにより適切なものがある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e5935-105">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="e5935-106">一般的に、コンボボックスは、推奨される選択肢のリストがある場合に適しています。また、リストボックスは、入力を一覧の内容に限定する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="e5935-106">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="e5935-107">コンボボックスにはテキストボックスフィールドが含まれているので、一覧にない選択肢を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5935-107">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="e5935-108">この例外は、 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> プロパティがに設定されている場合に発生し <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> ます。</span><span class="sxs-lookup"><span data-stu-id="e5935-108">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="e5935-109">この場合、最初の文字を入力すると、コントロールによって項目が選択されます。</span><span class="sxs-lookup"><span data-stu-id="e5935-109">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="e5935-110">また、コンボボックスでは、フォーム上の領域が節約されます。</span><span class="sxs-lookup"><span data-stu-id="e5935-110">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="e5935-111">ユーザーが下矢印をクリックするまでは完全な一覧が表示されないため、コンボボックスは、リストボックスが収まらない小さなスペースに簡単に収めることができます。</span><span class="sxs-lookup"><span data-stu-id="e5935-111">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="e5935-112">例外は、プロパティがに設定されている場合です <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> <xref:System.Windows.Forms.ComboBoxStyle.Simple> 。完全な一覧が表示されます。コンボボックスは、リストボックスの場合よりも多くの領域を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e5935-112">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5935-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5935-113">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="e5935-114">方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="e5935-114">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="e5935-115">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える</span><span class="sxs-lookup"><span data-stu-id="e5935-115">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="e5935-116">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="e5935-116">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
