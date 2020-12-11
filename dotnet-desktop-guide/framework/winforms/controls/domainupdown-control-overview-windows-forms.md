---
title: DomainUpDown コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981531"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="d3bec-102">DomainUpDown コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d3bec-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="d3bec-103">Windows フォームコントロールは、基本的には、 <xref:System.Windows.Forms.DomainUpDown> テキストボックスと、リストを上または下に移動するためのボタンの組み合わせで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d3bec-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="d3bec-104">コントロールは、選択肢の一覧からテキスト文字列を表示して設定します。</span><span class="sxs-lookup"><span data-stu-id="d3bec-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="d3bec-105">ユーザーは上下のボタンをクリックして一覧内を移動し、上下の方向キーを押すか、リスト内の項目に一致する文字列を入力することで、文字列を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d3bec-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="d3bec-106">このコントロールの1つの使用方法は、アルファベット順に並べ替えられた名前のリストから項目を選択することです。</span><span class="sxs-lookup"><span data-stu-id="d3bec-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3bec-107">リストを並べ替えるには、プロパティをに設定し <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="d3bec-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="d3bec-108">このコントロールの機能は、リストボックスまたはコンボボックスとよく似ていますが、スペースが非常に小さくなります。</span><span class="sxs-lookup"><span data-stu-id="d3bec-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="d3bec-109">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3bec-109">Key Properties</span></span>  
 <span data-ttu-id="d3bec-110">コントロールの主要なプロパティは、、、 <xref:System.Windows.Forms.DomainUpDown.Items%2A> <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> および <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> です。</span><span class="sxs-lookup"><span data-stu-id="d3bec-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="d3bec-111">プロパティは、 <xref:System.Windows.Forms.DomainUpDown.Items%2A> テキスト値がコントロールに表示されるオブジェクトのリストを格納します。</span><span class="sxs-lookup"><span data-stu-id="d3bec-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="d3bec-112"><xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>がに設定されている場合 `false` 、コントロールは、ユーザーが入力してリスト内の値と照合するテキストを自動的に完了します。</span><span class="sxs-lookup"><span data-stu-id="d3bec-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="d3bec-113"><xref:System.Windows.Forms.DomainUpDown.Wrap%2A>がに設定されている場合 `true` 、最後の項目を超えてスクロールすると、リストの最初の項目に移動します。逆の場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="d3bec-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="d3bec-114">コントロールの主要なメソッドは <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> と <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> です。</span><span class="sxs-lookup"><span data-stu-id="d3bec-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="d3bec-115">このコントロールは、テキスト文字列のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3bec-115">This control displays only text strings.</span></span> <span data-ttu-id="d3bec-116">数値を表示するコントロールが必要な場合は、コントロールを使用し <xref:System.Windows.Forms.NumericUpDown> ます。</span><span class="sxs-lookup"><span data-stu-id="d3bec-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="d3bec-117">詳細については、「 [NumericUpDown Control の概要](numericupdown-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3bec-117">For more information, see [NumericUpDown Control Overview](numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bec-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3bec-118">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="d3bec-119">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="d3bec-119">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
