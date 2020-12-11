---
title: ボタンコントロールを選択する方法
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982691"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="2ddb0-102">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="2ddb0-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="2ddb0-103">Windows フォームボタンは、次の方法で選択できます。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="2ddb0-104">マウスを使用してボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="2ddb0-105">ボタンのイベントを <xref:System.Windows.Forms.Control.Click> コードで呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="2ddb0-106">TAB キーを押してボタンにフォーカスを移動し、SPACE キーまたは ENTER キーを押してボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="2ddb0-107">ボタンのアクセスキー (ALT + 下線付きの文字) を押します。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="2ddb0-108">アクセスキーの詳細については、「 [方法: Windows フォームコントロールのアクセスキーを作成する](how-to-create-access-keys-for-windows-forms-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="2ddb0-109">ボタンがフォームの "accept" ボタンの場合は、別のコントロールがフォーカスを持っている場合でも、ENTER キーを押すとボタンが選択されます。ただし、他のコントロールが別のボタン、複数行のテキストボックス、または ENTER キーをトラップするカスタムコントロールである場合は例外です。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="2ddb0-110">ボタンがフォームの [キャンセル] ボタンの場合、ESC キーを押すと、別のコントロールにフォーカスがある場合でも、ボタンが選択されます。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="2ddb0-111">メソッドを呼び出し <xref:System.Windows.Forms.Button.PerformClick%2A> て、プログラムでボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ddb0-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ddb0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ddb0-112">See also</span></span>

- [<span data-ttu-id="2ddb0-113">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2ddb0-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="2ddb0-114">方法 : Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="2ddb0-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="2ddb0-115">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="2ddb0-115">Button Control</span></span>](button-control-windows-forms.md)
