---
title: '方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する'
description: プログラムによって、または Visual Studio の Windows フォームデザイナーで、コントロールのツールヒントを設定する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983032"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="10168-103">方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する</span><span class="sxs-lookup"><span data-stu-id="10168-103">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="10168-104"><xref:System.Windows.Forms.ToolTip>コードまたは Visual Studio の Windows フォームデザイナーで文字列を設定できます。</span><span class="sxs-lookup"><span data-stu-id="10168-104">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="10168-105">コンポーネントの詳細については <xref:System.Windows.Forms.ToolTip> 、「 [ツールヒントコンポーネントの概要](tooltip-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10168-105">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="10168-106">プログラムによるツールヒントの設定</span><span class="sxs-lookup"><span data-stu-id="10168-106">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="10168-107">ツールヒントを表示するコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="10168-107">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="10168-108"><xref:System.Windows.Forms.ToolTip.SetToolTip%2A>コンポーネントのメソッドを使用し <xref:System.Windows.Forms.ToolTip> ます。</span><span class="sxs-lookup"><span data-stu-id="10168-108">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="10168-109">デザイナーでのツールヒントの設定</span><span class="sxs-lookup"><span data-stu-id="10168-109">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="10168-110">Visual Studio で、コンポーネントを <xref:System.Windows.Forms.ToolTip> フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="10168-110">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="10168-111">ツールヒントを表示するコントロールを選択するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="10168-111">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="10168-112">[ **プロパティ** ] ウィンドウで、ToolTip1 Value の **ツールヒント** を適切なテキスト文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="10168-112">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="10168-113">プログラムによってツールヒントを削除するには</span><span class="sxs-lookup"><span data-stu-id="10168-113">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="10168-114"><xref:System.Windows.Forms.ToolTip.SetToolTip%2A>コンポーネントのメソッドを使用し <xref:System.Windows.Forms.ToolTip> ます。</span><span class="sxs-lookup"><span data-stu-id="10168-114">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="10168-115">デザイナーのツールヒントを削除する</span><span class="sxs-lookup"><span data-stu-id="10168-115">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="10168-116">Visual Studio で、ツールヒントを表示しているコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="10168-116">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="10168-117">[ **プロパティ** ] ウィンドウで、 **ToolTip1 のツールヒント** のテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="10168-117">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="10168-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="10168-118">See also</span></span>

- [<span data-ttu-id="10168-119">ToolTip コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="10168-119">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="10168-120">方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更する</span><span class="sxs-lookup"><span data-stu-id="10168-120">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="10168-121">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10168-121">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
