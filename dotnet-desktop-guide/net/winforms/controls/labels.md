---
title: ラベル コントロール
description: .NET 用の Windows フォームの Label コントロールについて説明します。 ラベルを使用して、ユーザーがビジュアル要素を識別できるようにします。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.openlocfilehash: 6f669b7aef1182c35e125ff8dd3ca5ccb299b898
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942271"
---
# <a name="label-control-overview-windows-forms-net"></a><span data-ttu-id="9beef-104">Label コントロールの概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="9beef-104">Label control overview (Windows Forms .NET)</span></span>

<span data-ttu-id="9beef-105">Windows フォームの <xref:System.Windows.Forms.Label> コントロールは、ユーザーが編集できないテキストを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9beef-105">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text that cannot be edited by the user.</span></span> <span data-ttu-id="9beef-106">これらは、フォーム上のオブジェクトを識別したり、特定のコントロールが表すものや実行内容を説明したりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9beef-106">They're used to identify objects on a form and to provide a description of what a certain control represents or does.</span></span> <span data-ttu-id="9beef-107">たとえば、ラベルを使用すると、テキスト ボックス、リスト ボックス、コンボ ボックスなどにわかりやすいキャプションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9beef-107">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="9beef-108">また、実行時にイベントに応答して、ラベルによって表示されるテキストを変更するコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="9beef-108">You can also write code that changes the text displayed by a label in response to events at run time.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="working-with-the-label-control"></a><span data-ttu-id="9beef-109">Label コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="9beef-109">Working with the Label Control</span></span>  

<span data-ttu-id="9beef-110"><xref:System.Windows.Forms.Label> コントロールはフォーカスを受け取ることができないため、他のコントロールのアクセス キーを作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9beef-110">Because the <xref:System.Windows.Forms.Label> control can't receive focus, it can be used to create access keys for other controls.</span></span> <span data-ttu-id="9beef-111">アクセス キーを使用すると、ユーザーは、選択したアクセス キーを使用して <kbd>Alt</kbd> キーを押すことで、タブ オーダーで次のコントロールにフォーカスすることができます。</span><span class="sxs-lookup"><span data-stu-id="9beef-111">An access key allows a user to focus the next control in tab order by pressing the <kbd>Alt</kbd> key with the chosen access key.</span></span> <span data-ttu-id="9beef-112">詳細については、「[ラベルを使用してコントロールにフォーカスを設定する](how-to-create-access-keys.md#use-a-label-to-focus-a-control)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9beef-112">For more information, see [Use a label to focus a control](how-to-create-access-keys.md#use-a-label-to-focus-a-control).</span></span>
  
<span data-ttu-id="9beef-113">ラベルに表示されるキャプションは、<xref:System.Windows.Forms.Label.Text%2A> プロパティに含まれています。</span><span class="sxs-lookup"><span data-stu-id="9beef-113">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="9beef-114"><xref:System.Windows.Forms.Label.TextAlign%2A> プロパティを使用すると、ラベル内のテキストの配置を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9beef-114">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="9beef-115">詳細については、「[方法:Windows フォーム コントロールによって表示されるテキストを設定する](how-to-set-the-display-text.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9beef-115">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-display-text.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9beef-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9beef-116">See also</span></span>

- [<span data-ttu-id="9beef-117">ラベルを使用してコントロールにフォーカスを設定する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="9beef-117">Use a label to focus a control (Windows Forms .NET)</span></span>](how-to-create-access-keys.md#use-a-label-to-focus-a-control)
- [<span data-ttu-id="9beef-118">方法: コントロールによって表示されるテキストを設定する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="9beef-118">How to: Set the text displayed by a control (Windows Forms .NET)</span></span>](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
