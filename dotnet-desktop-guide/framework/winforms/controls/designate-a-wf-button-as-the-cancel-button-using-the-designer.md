---
title: デザイナーを使用してボタンを [キャンセル] ボタンとして指定する
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974183"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="0c09b-102">方法: デザイナーを使用して Windows フォームの Button コントロールをキャンセル ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="0c09b-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="0c09b-103">任意の Windows フォームで、 <xref:System.Windows.Forms.Button> [キャンセル] ボタンとしてコントロールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c09b-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="0c09b-104">フォーム上の他のコントロールにフォーカスがあるかどうかに関係なく、ユーザーが ESC キーを押すたびに [キャンセル] ボタンがクリックされます。</span><span class="sxs-lookup"><span data-stu-id="0c09b-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="0c09b-105">このようなボタンは、通常、ユーザーがアクションをコミットせずに操作をすばやく終了できるようにプログラミングされています。</span><span class="sxs-lookup"><span data-stu-id="0c09b-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="0c09b-106">[キャンセル] ボタンを指定するには</span><span class="sxs-lookup"><span data-stu-id="0c09b-106">To designate the cancel button</span></span>

1. <span data-ttu-id="0c09b-107">ボタンが存在するフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c09b-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="0c09b-108">[ **プロパティ** ] ウィンドウで、フォームの <xref:System.Windows.Forms.Form.CancelButton%2A> プロパティを <xref:System.Windows.Forms.Button> コントロールの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c09b-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c09b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c09b-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="0c09b-110">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0c09b-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="0c09b-111">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="0c09b-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="0c09b-112">方法 : Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="0c09b-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="0c09b-113">方法: デザイナーを使用して Windows フォームの Button コントロールを承認ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="0c09b-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="0c09b-114">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="0c09b-114">Button Control</span></span>](button-control-windows-forms.md)
