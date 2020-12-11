---
title: '方法: デザイナーを使用してピクチャを読み込む'
description: Windows フォーム PictureBox コントロールを使用して、デザイン時にフォームに画像を読み込んで表示する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982736"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="c9ea0-103">方法 : デザイナーを使用してピクチャを読み込む (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="c9ea0-103">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="c9ea0-104">Windows フォームコントロールを使用すると、 <xref:System.Windows.Forms.PictureBox> <xref:System.Windows.Forms.PictureBox.Image%2A> プロパティを有効な画像に設定することによって、デザイン時にフォームの画像を読み込んで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-104">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="c9ea0-105">次の表に、許容されるファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-105">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="c9ea0-106">Type</span><span class="sxs-lookup"><span data-stu-id="c9ea0-106">Type</span></span>|<span data-ttu-id="c9ea0-107">ファイル名の拡張子</span><span class="sxs-lookup"><span data-stu-id="c9ea0-107">File name extension</span></span>|
|---|---|
|<span data-ttu-id="c9ea0-108">Bitmap</span><span class="sxs-lookup"><span data-stu-id="c9ea0-108">Bitmap</span></span>|<span data-ttu-id="c9ea0-109">.bmp</span><span class="sxs-lookup"><span data-stu-id="c9ea0-109">.bmp</span></span>|
|<span data-ttu-id="c9ea0-110">アイコン</span><span class="sxs-lookup"><span data-stu-id="c9ea0-110">Icon</span></span>|<span data-ttu-id="c9ea0-111">.ico</span><span class="sxs-lookup"><span data-stu-id="c9ea0-111">.ico</span></span>|
|<span data-ttu-id="c9ea0-112">GIF</span><span class="sxs-lookup"><span data-stu-id="c9ea0-112">GIF</span></span>|<span data-ttu-id="c9ea0-113">.gif</span><span class="sxs-lookup"><span data-stu-id="c9ea0-113">.gif</span></span>|
|<span data-ttu-id="c9ea0-114">Metafile</span><span class="sxs-lookup"><span data-stu-id="c9ea0-114">Metafile</span></span>|<span data-ttu-id="c9ea0-115">.wmf</span><span class="sxs-lookup"><span data-stu-id="c9ea0-115">.wmf</span></span>|
|<span data-ttu-id="c9ea0-116">JPEG</span><span class="sxs-lookup"><span data-stu-id="c9ea0-116">JPEG</span></span>|<span data-ttu-id="c9ea0-117">.jpg</span><span class="sxs-lookup"><span data-stu-id="c9ea0-117">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="c9ea0-118">デザイン時に画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="c9ea0-118">To display a picture at design time</span></span>

1. <span data-ttu-id="c9ea0-119"><xref:System.Windows.Forms.PictureBox>フォーム上にコントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-119">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="c9ea0-120">[ **プロパティ** ] ウィンドウで、プロパティを選択し、 <xref:System.Windows.Forms.PictureBox.Image%2A> 省略記号ボタンを選択して [ **開く** ] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-120">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="c9ea0-121">特定のファイルの種類 (.gif ファイルなど) を探している場合は、[ **ファイルの種類** ] ボックスでそれを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-121">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="c9ea0-122">表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-122">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="c9ea0-123">デザイン時に画像をクリアするには</span><span class="sxs-lookup"><span data-stu-id="c9ea0-123">To clear the picture at design time</span></span>

1. <span data-ttu-id="c9ea0-124">[ **プロパティ** ] ウィンドウで、プロパティを選択し <xref:System.Windows.Forms.PictureBox.Image%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-124">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="c9ea0-125">イメージオブジェクトの名前の左側に表示される小さいサムネイル画像を右クリックし、[ **リセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9ea0-125">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9ea0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9ea0-126">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="c9ea0-127">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="c9ea0-127">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="c9ea0-128">方法: 実行時にピクチャのサイズまたは配置を変更する</span><span class="sxs-lookup"><span data-stu-id="c9ea0-128">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="c9ea0-129">方法: 実行時にピクチャを設定する</span><span class="sxs-lookup"><span data-stu-id="c9ea0-129">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="c9ea0-130">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="c9ea0-130">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
