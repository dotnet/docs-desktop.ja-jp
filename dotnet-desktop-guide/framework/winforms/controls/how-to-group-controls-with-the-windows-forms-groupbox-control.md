---
title: GroupBox コントロールを使用したコントロールのグループ化
description: 関連する要素の視覚的なグループを作成できるように、Windows フォーム GroupBox コントロールを使用してコントロールをグループ化する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982131"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="32667-103">方法: Windows フォーム GroupBox コントロールを使用してコントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="32667-103">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="32667-104">Windows フォーム <xref:System.Windows.Forms.GroupBox> コントロールは、他のコントロールをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="32667-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="32667-105">コントロールをグループ化する理由は3つあります。</span><span class="sxs-lookup"><span data-stu-id="32667-105">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="32667-106">クリアユーザーインターフェイスに関連するフォーム要素の視覚的なグループ化を作成するには</span><span class="sxs-lookup"><span data-stu-id="32667-106">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="32667-107">プログラムによるグループ化 (オプションボタンなど) を作成する場合は。</span><span class="sxs-lookup"><span data-stu-id="32667-107">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="32667-108">デザイン時にコントロールを1つの単位として移動する場合は。</span><span class="sxs-lookup"><span data-stu-id="32667-108">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="32667-109">コントロールのグループを作成するには</span><span class="sxs-lookup"><span data-stu-id="32667-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="32667-110"><xref:System.Windows.Forms.GroupBox>フォーム上にコントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="32667-110">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="32667-111">グループボックスに他のコントロールを追加し、それぞれをグループボックス内に描画します。</span><span class="sxs-lookup"><span data-stu-id="32667-111">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="32667-112">グループボックスに含める既存のコントロールがある場合は、すべてのコントロールを選択してクリップボードに <xref:System.Windows.Forms.GroupBox> 貼り付け、コントロールを選択して、グループボックスに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="32667-112">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="32667-113">また、[グループ] ボックスにドラッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="32667-113">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="32667-114"><xref:System.Windows.Forms.GroupBox.Text%2A>グループボックスのプロパティを適切なキャプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="32667-114">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32667-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="32667-115">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="32667-116">GroupBox コントロール</span><span class="sxs-lookup"><span data-stu-id="32667-116">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
