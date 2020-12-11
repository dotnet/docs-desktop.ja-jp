---
title: '方法: デザイナーを使って ImageList イメージを追加または削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982264"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="426e2-102">方法: デザイナーを使って ImageList イメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="426e2-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="426e2-103">コンポーネントにイメージを追加するには、 <xref:System.Windows.Forms.ImageList> さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="426e2-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="426e2-104">に関連付けられたスマートタグを使用すると、イメージをすばやく追加できます <xref:System.Windows.Forms.ImageList> 。また、で他のプロパティをいくつか設定する場合は、 <xref:System.Windows.Forms.ImageList> プロパティウィンドウで画像を追加する方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="426e2-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="426e2-105">コードを使用してイメージを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="426e2-105">You can also add images by using code.</span></span> <span data-ttu-id="426e2-106">コードを使用してイメージを追加する方法の詳細については、「 [方法: Windows フォーム ImageList コンポーネントを使用してイメージを追加または削除](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="426e2-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="426e2-107">通常は、 <xref:System.Windows.Forms.ImageList> コントロールに関連付けられる前にコンポーネントにイメージを設定しますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="426e2-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="426e2-108">プロパティウィンドウを使用してイメージを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="426e2-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="426e2-109">コンポーネントを選択 <xref:System.Windows.Forms.ImageList> するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="426e2-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="426e2-110">プロパティウィンドウで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ImageList.Images%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="426e2-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="426e2-111">**イメージコレクションエディター** で、[**追加**] または [**削除**] をクリックして、一覧からイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="426e2-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="426e2-112">スマートタグを使用してイメージを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="426e2-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="426e2-113">コンポーネントを選択 <xref:System.Windows.Forms.ImageList> するか、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="426e2-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="426e2-114">デザイナーアクショングリフをクリックします (</span><span class="sxs-lookup"><span data-stu-id="426e2-114">Click the designer actions glyph (</span></span>![小さい黒い矢印](./media/designer-actions-glyph.gif)<span data-ttu-id="426e2-116">)</span><span class="sxs-lookup"><span data-stu-id="426e2-116">)</span></span>

3. <span data-ttu-id="426e2-117">[ **ImageList Tasks** ] ダイアログボックスで、[ **Images の選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="426e2-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="426e2-118">**イメージコレクションエディター** で、[**追加**] または [**削除**] をクリックして、一覧からイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="426e2-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="426e2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="426e2-119">See also</span></span>

- [<span data-ttu-id="426e2-120">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="426e2-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="426e2-121">チュートリアル: デザイン アクションを使って一般的なタスクを実行する</span><span class="sxs-lookup"><span data-stu-id="426e2-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="426e2-122">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="426e2-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
