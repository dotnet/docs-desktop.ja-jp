---
title: Label コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 1ca14553c7cb51d2b7a329950aeaec4c0439762a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982967"
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="4c2f3-102">Label コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="4c2f3-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="4c2f3-103">Windows フォーム <xref:System.Windows.Forms.Label> コントロールは、ユーザーが編集できないテキストまたはイメージを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="4c2f3-104">これらは、フォーム上のオブジェクトを識別するために使用されます。たとえば、をクリックした場合、またはアプリケーションの実行時のイベントまたはプロセスに応答して情報を表示するために、特定のコントロールの動作についての説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="4c2f3-105">たとえば、ラベルを使用して、テキストボックス、リストボックス、コンボボックスなどにわかりやすいキャプションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="4c2f3-106">また、実行時にイベントに応答してラベルによって表示されるテキストを変更するコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="4c2f3-107">たとえば、アプリケーションの変更を処理するのに数分かかる場合、処理状態メッセージをラベルに表示できます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="4c2f3-108">ラベルコントロールの操作</span><span class="sxs-lookup"><span data-stu-id="4c2f3-108">Working with the Label Control</span></span>  
 <span data-ttu-id="4c2f3-109">コントロールは <xref:System.Windows.Forms.Label> フォーカスを受け取ることができないため、他のコントロールのアクセスキーを作成するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="4c2f3-110">アクセスキーを使用すると、ユーザーは ALT キーを押しながらアクセスキーを押すことによって、もう一方のコントロールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="4c2f3-111">詳細については、「 [Windows フォームコントロールのアクセスキーの作成](how-to-create-access-keys-for-windows-forms-controls.md) 」および「 [方法: Windows フォームラベルコントロールを使用してアクセスキーを作成する](how-to-create-access-keys-with-windows-forms-label-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-111">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="4c2f3-112">ラベルに表示されるキャプションは、プロパティに含まれてい <xref:System.Windows.Forms.Label.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="4c2f3-113"><xref:System.Windows.Forms.Label.TextAlign%2A>プロパティを使用すると、ラベル内のテキストの配置を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="4c2f3-114">詳細については、「 [方法: Windows フォームコントロールによって表示されるテキストを設定する](how-to-set-the-text-displayed-by-a-windows-forms-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c2f3-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2f3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c2f3-115">See also</span></span>

- <xref:System.Windows.Forms.Label>
- [<span data-ttu-id="4c2f3-116">方法: Windows フォーム Label コントロールのサイズを内容に合わせて変更する</span><span class="sxs-lookup"><span data-stu-id="4c2f3-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="4c2f3-117">方法: Windows フォームの Label コントロールでアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="4c2f3-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
