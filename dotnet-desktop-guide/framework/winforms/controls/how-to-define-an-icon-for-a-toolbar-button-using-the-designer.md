---
title: '方法: デザイナーを使って ToolBar ボタンのアイコンを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980876"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="17fd8-102">方法: デザイナーを使って ToolBar ボタンのアイコンを定義する</span><span class="sxs-lookup"><span data-stu-id="17fd8-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="17fd8-103"><xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="17fd8-104"><xref:System.Windows.Forms.ToolBar> ボタンは、ユーザーが簡単に識別できるように、それらの中にアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="17fd8-105">これは、コンポーネントにイメージを追加 <xref:System.Windows.Forms.ImageList> し、コントロールに関連付けることによって実現され <xref:System.Windows.Forms.ToolBar> ます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="17fd8-106">次の手順では、コントロールとコンポーネントを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ImageList> 。</span><span class="sxs-lookup"><span data-stu-id="17fd8-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="17fd8-107">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17fd8-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="17fd8-108">デザイン時にツールバーボタンのアイコンを設定するには</span><span class="sxs-lookup"><span data-stu-id="17fd8-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="17fd8-109">コンポーネントにイメージを追加 <xref:System.Windows.Forms.ImageList> します。</span><span class="sxs-lookup"><span data-stu-id="17fd8-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="17fd8-110">詳細については、「 [方法: デザイナーを使用して ImageList イメージを追加または削除する](how-to-add-or-remove-imagelist-images-with-the-designer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17fd8-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="17fd8-111"><xref:System.Windows.Forms.ToolBar>フォーム上のコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="17fd8-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="17fd8-112">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.ToolBar> コントロールの <xref:System.Windows.Forms.ToolBar.ImageList%2A> プロパティをコンポーネントに設定し <xref:System.Windows.Forms.ImageList> ます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="17fd8-113"><xref:System.Windows.Forms.ToolBar>コントロールのプロパティをクリックし <xref:System.Windows.Forms.ToolBar.Buttons%2A> て選択し、省略記号 ([ ![ Visual Studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして ](./media/visual-studio-ellipsis-button.png) **ToolBarButton Collection エディター** を開きます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="17fd8-114">コントロールにボタンを追加するには、[ **追加** ] ボタンを使用し <xref:System.Windows.Forms.ToolBar> ます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="17fd8-115">**ToolBarButton Collection エディター** の右側にあるペインに表示される [**プロパティ**] ウィンドウで、 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 各ツールバーボタンのプロパティを、コンポーネントに追加したイメージから描画されるリスト内の値のいずれかに設定し <xref:System.Windows.Forms.ImageList> ます。</span><span class="sxs-lookup"><span data-stu-id="17fd8-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="17fd8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="17fd8-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="17fd8-117">方法: ツール バー ボタンのメニュー イベントをトリガーする</span><span class="sxs-lookup"><span data-stu-id="17fd8-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="17fd8-118">ToolBar コントロール</span><span class="sxs-lookup"><span data-stu-id="17fd8-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="17fd8-119">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17fd8-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
