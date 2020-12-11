---
title: デザイナーを使用して ListView コントロールのタイルビューを有効にする
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981528"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="5be37-102">方法: デザイナーを使って Windows フォーム ListView コントロールの "並べて表示" ビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="5be37-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="5be37-103">コントロールのタイルビュー機能を使用すると、 <xref:System.Windows.Forms.ListView> グラフィカルな情報とテキスト情報の間に視覚的なバランスを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5be37-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="5be37-104">並べて表示ビューの項目で表示されるテキスト情報は、詳細ビュー用に定義されている列情報と同じ情報です。</span><span class="sxs-lookup"><span data-stu-id="5be37-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="5be37-105">並べて表示ビューは、コントロールのグループ化機能または挿入マーク機能と組み合わせて使用 <xref:System.Windows.Forms.ListView> します。</span><span class="sxs-lookup"><span data-stu-id="5be37-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="5be37-106">タイルビューでは、次の図に示すように、32 x 32 アイコンと数行のテキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5be37-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="5be37-107">![ListView コントロール内の並べて表示ビュー](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "並べて表示ビューのアイコンとテキスト")</span><span class="sxs-lookup"><span data-stu-id="5be37-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="5be37-108">タイルビューのプロパティとメソッドを使用すると、各項目に対して表示する列フィールドを指定したり、タイルビューウィンドウ内のすべての項目のサイズと外観をまとめて制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5be37-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="5be37-109">わかりやすくするために、タイルのテキストの最初の行は常に項目の名前です。変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5be37-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="5be37-110">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="5be37-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="5be37-111">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5be37-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="5be37-112">デザイナーでタイルビューを設定するには</span><span class="sxs-lookup"><span data-stu-id="5be37-112">To set tile view in the designer</span></span>

1. <span data-ttu-id="5be37-113">Visual Studio で、フォーム上のコントロールを選択し <xref:System.Windows.Forms.ListView> ます。</span><span class="sxs-lookup"><span data-stu-id="5be37-113">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="5be37-114">[ **プロパティ** ] ウィンドウで、プロパティを選択し、 <xref:System.Windows.Forms.ListView.View%2A> [ **タイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5be37-114">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5be37-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5be37-115">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="5be37-116">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5be37-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
