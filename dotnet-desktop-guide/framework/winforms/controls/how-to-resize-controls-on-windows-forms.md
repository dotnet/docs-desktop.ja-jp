---
title: コントロールのサイズを変更する
ms.date: 03/30/2017
f1_keywords:
- Size.Height
- Size.Width
helpviewer_keywords:
- controls [Windows Forms], resizing
- size [Windows Forms], controls
- Windows Forms controls, size
ms.assetid: d2dba441-a8c0-4705-b8e8-2e5d86d6e7ec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 771de6e3962df241357307b0af7682eb45283892
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974754"
---
# <a name="how-to-resize-controls-on-windows-forms"></a><span data-ttu-id="84a41-102">方法: Windows フォーム上のコントロールのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="84a41-102">How to: Resize controls on Windows Forms</span></span>

<span data-ttu-id="84a41-103">個々のコントロールのサイズを変更したり、コントロールやコントロールなど、同じ種類または異なる種類の複数のコントロールのサイズを変更したりでき <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox> ます。</span><span class="sxs-lookup"><span data-stu-id="84a41-103">You can resize individual controls, and you can resize multiple controls of the same or different kind, such as <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.GroupBox> controls.</span></span>

## <a name="to-resize-a-control"></a><span data-ttu-id="84a41-104">コントロールのサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="84a41-104">To resize a control</span></span>

<span data-ttu-id="84a41-105">Visual Studio で、サイズを変更するコントロールを選択し、8つのサイズ変更ハンドルのいずれかをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="84a41-105">In Visual Studio, select the control to be resized and drag one of the eight sizing handles.</span></span>

> [!NOTE]
> <span data-ttu-id="84a41-106">コントロールを選択し、 **shift** キーを押しながら **方向** キーを押すと、コントロールのサイズが一度に1ピクセルずつ変更されます。</span><span class="sxs-lookup"><span data-stu-id="84a41-106">Select the control and press the **arrow** keys while holding down the **Shift** key to resize the control one pixel at a time.</span></span> <span data-ttu-id="84a41-107">**Shift** キーまたは **Ctrl** キーを押しながら **下方向** キーまたは **右方向** キーを押すと、コントロールのサイズが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="84a41-107">Press the **down arrow** or **right arrow** keys while holding down the **Shift** and **Ctrl** keys to resize the control in large increments.</span></span>

## <a name="to-resize-multiple-controls-on-a-form"></a><span data-ttu-id="84a41-108">フォーム上の複数のコントロールのサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="84a41-108">To resize multiple controls on a form</span></span>

1. <span data-ttu-id="84a41-109">Visual Studio で、 **Ctrl** キーまたは **Shift** キーを押しながら、サイズを変更するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="84a41-109">In Visual Studio, hold down the **Ctrl** or **Shift** key and select the controls you want to resize.</span></span> <span data-ttu-id="84a41-110">選択した最初のコントロールのサイズは、他のコントロールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="84a41-110">The size of the first control you select is used for the other controls.</span></span>

2. <span data-ttu-id="84a41-111">[ **書式** ] メニューの [ **同じサイズに揃える**] をクリックし、4つのオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="84a41-111">On the **Format** menu, choose **Make Same Size**, and select one of the four options.</span></span> <span data-ttu-id="84a41-112">最初の3つのコマンドは、最初に選択されたコントロールに合わせてコントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="84a41-112">The first three commands change the dimensions of the controls to match the first-selected control.</span></span>

## <a name="see-also"></a><span data-ttu-id="84a41-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="84a41-113">See also</span></span>

- [<span data-ttu-id="84a41-114">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="84a41-114">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="84a41-115">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="84a41-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="84a41-116">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="84a41-116">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="84a41-117">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="84a41-117">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="84a41-118">[方法 : デザイナーを使用して Windows フォームのサイズを変更する](/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="84a41-118">[How to: Resize Windows Forms Using the Designer](/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span></span>
