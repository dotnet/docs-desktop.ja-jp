---
title: ListView コントロールのアイコンを表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980839"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="52f51-102">方法: Windows フォーム ListView コントロールのアイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="52f51-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="52f51-103">Windows フォームコントロールでは、 <xref:System.Windows.Forms.ListView> 3 つのイメージリストのアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="52f51-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="52f51-104">List、Details、および SmallIcon の各ビューには、プロパティで指定したイメージリストのイメージが表示され <xref:System.Windows.Forms.ListView.SmallImageList%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="52f51-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="52f51-105">LargeIcon ビューには、プロパティで指定されたイメージリストのイメージが表示され <xref:System.Windows.Forms.ListView.LargeImageList%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="52f51-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="52f51-106">リストビューでは、大きいアイコンまたは小さいアイコンの横にある、プロパティに設定された追加のアイコンのセットを表示することもでき <xref:System.Windows.Forms.ListView.StateImageList%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="52f51-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="52f51-107">イメージリストの詳細については、「 [Imagelist コンポーネント](imagelist-component-windows-forms.md) 」および「 [方法: Windows フォーム imagelist コンポーネントを使用してイメージを追加または削除する](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52f51-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="52f51-108">リストビューに画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="52f51-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="52f51-109">適切なプロパティ ( <xref:System.Windows.Forms.ListView.SmallImageList%2A> 、 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 、または <xref:System.Windows.Forms.ListView.StateImageList%2A> ) を、使用する既存のコンポーネントに設定し <xref:System.Windows.Forms.ImageList> ます。</span><span class="sxs-lookup"><span data-stu-id="52f51-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="52f51-110">これらのプロパティは、デザイナーでプロパティウィンドウまたはコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="52f51-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="52f51-111"><xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> アイコンが関連付けられている各リスト項目のプロパティまたはプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="52f51-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="52f51-112">これらのプロパティは、コードで設定することも、 **ListViewItem Collection エディター** 内で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="52f51-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="52f51-113">**ListViewItem Collection エディター** を開くには、[ ![ ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A> **プロパティ**] ウィンドウのプロパティの横にある省略記号ボタン ([...] プロパティウィンドウ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52f51-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="52f51-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="52f51-114">See also</span></span>

- [<span data-ttu-id="52f51-115">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="52f51-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="52f51-116">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="52f51-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="52f51-117">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="52f51-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="52f51-118">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="52f51-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="52f51-119">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="52f51-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
