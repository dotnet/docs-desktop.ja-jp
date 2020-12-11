---
title: デザイナーを使用して DataGridView コントロールに交互の行のスタイルを設定する
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 74f65d03a359136de943f8a2937ed5e5f1e62519
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974726"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="9e5b5-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="9e5b5-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="9e5b5-103">多くの場合、表形式のデータは、交互の行が異なる背景色を持つ、台帳に似た形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="9e5b5-104">この形式を使用すると、多数の列がある幅の広いテーブルで、ユーザーが各行にあるセルを簡単に識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="9e5b5-105"><xref:System.Windows.Forms.DataGridView> コントロールを使用すると、1 行おきの完全なスタイル情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="9e5b5-106">背景色に加えて、前景色やフォントなどのスタイル特性を使用して、交互の行を区別することができます。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="9e5b5-107">詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="9e5b5-108">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9e5b5-109">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="9e5b5-110">交互の行のスタイルを定義する</span><span class="sxs-lookup"><span data-stu-id="9e5b5-110">Define styles for alternating rows</span></span>

1. <span data-ttu-id="9e5b5-111"><xref:System.Windows.Forms.DataGridView>デザイナーでコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-111">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="9e5b5-112">[ **プロパティ** ] ウィンドウで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-112">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="9e5b5-113">[ **CellStyle ビルダー** ] ダイアログボックスで、プロパティを設定してスタイルを定義し、 **プレビュー** ウィンドウを使用して選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-113">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="9e5b5-114">指定したスタイルは、コントロールに表示される他のすべての行に使用され、2番目のスタイルから始まります。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-114">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="9e5b5-115">残りの行のスタイルを定義するには、プロパティを使用して手順 2. と 3. を繰り返し <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-115">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e5b5-116">複数のプロパティから継承されたスタイルを使用して、セルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-116">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="9e5b5-117">スタイルの継承の詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e5b5-117">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e5b5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e5b5-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="9e5b5-119">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="9e5b5-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9e5b5-120">Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定</span><span class="sxs-lookup"><span data-stu-id="9e5b5-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9e5b5-121">Windows フォーム DataGridView コントロールでのデザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="9e5b5-121">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9e5b5-122">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="9e5b5-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="9e5b5-123">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="9e5b5-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
