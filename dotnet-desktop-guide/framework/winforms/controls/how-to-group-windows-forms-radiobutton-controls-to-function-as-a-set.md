---
title: Set RadioButton コントロールをセットとして機能するようにグループ化する
description: 他のセットとは独立して機能するように Windows フォーム RadioButton コントロールをグループ化する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 9f6795330922e739cca1f2b5c11bb2ec68bb4e84
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982484"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="09231-103">方法: セットとして機能する Windows フォーム RadioButton コントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="09231-103">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="09231-104">Windows フォーム <xref:System.Windows.Forms.RadioButton> コントロールは、ユーザーが2つ以上の設定を選択できるように設計されており、1つのプロシージャまたはオブジェクトに割り当てることができるのは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="09231-104">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="09231-105">たとえば、コントロールのグループでは、 <xref:System.Windows.Forms.RadioButton> 注文に対して選択されたパッケージキャリアを表示できますが、使用されるのは1つの配送業者だけです。</span><span class="sxs-lookup"><span data-stu-id="09231-105">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="09231-106">そのため <xref:System.Windows.Forms.RadioButton> 、機能グループの一部であっても、一度に1つだけ選択できます。</span><span class="sxs-lookup"><span data-stu-id="09231-106">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="09231-107">ラジオボタンをグループ化するには、コントロール、コントロール、フォームなどのコンテナー内にオプションボタンを描画し <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> ます。</span><span class="sxs-lookup"><span data-stu-id="09231-107">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="09231-108">フォームに直接追加されたすべてのラジオボタンは、1つのグループになります。</span><span class="sxs-lookup"><span data-stu-id="09231-108">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="09231-109">個別のグループを追加するには、パネルまたはグループボックス内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09231-109">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="09231-110">パネルまたはグループボックスの詳細については、「 [Panel コントロールの概要](panel-control-overview-windows-forms.md) 」または「 [GroupBox コントロールの概要](groupbox-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09231-110">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="09231-111">RadioButton コントロールを他のセットとは独立して機能するようにグループ化するには</span><span class="sxs-lookup"><span data-stu-id="09231-111">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="09231-112"><xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> **ツールボックス** の [ **Windows フォーム**] タブからコントロールまたはコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="09231-112">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="09231-113">コントロール <xref:System.Windows.Forms.RadioButton> またはコントロールにコントロールを描画 <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> します。</span><span class="sxs-lookup"><span data-stu-id="09231-113">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09231-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="09231-114">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="09231-115">RadioButton コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="09231-115">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="09231-116">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="09231-116">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="09231-117">GroupBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="09231-117">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="09231-118">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="09231-118">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="09231-119">RadioButton コントロール</span><span class="sxs-lookup"><span data-stu-id="09231-119">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
