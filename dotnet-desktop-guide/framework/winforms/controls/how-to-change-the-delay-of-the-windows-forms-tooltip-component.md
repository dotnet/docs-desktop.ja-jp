---
title: ツールヒントコンポーネントの遅延を変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982220"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="7de25-102">方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更する</span><span class="sxs-lookup"><span data-stu-id="7de25-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="7de25-103">Windows フォームコンポーネントに設定できる遅延値は複数あり <xref:System.Windows.Forms.ToolTip> ます。</span><span class="sxs-lookup"><span data-stu-id="7de25-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="7de25-104">これらのプロパティすべての測定単位はミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="7de25-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="7de25-105">プロパティは、 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> ツールヒント文字列を表示するために、関連付けられたコントロールをユーザーがポイントする必要がある期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="7de25-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="7de25-106">プロパティは、 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> ツールヒントに関連付けられたコントロール間でマウスを移動したときに、後続のツールヒント文字列が表示されるまでにかかる時間をミリ秒単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="7de25-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="7de25-107">プロパティは、 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> ツールヒント文字列を表示する時間の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="7de25-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="7de25-108">これらの値は、個別に設定するか、プロパティの値を設定することによって設定できます <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 。その他の遅延プロパティは、プロパティに割り当てられている値に基づいて設定され <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7de25-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="7de25-109">たとえば、が値 N に設定されていて、が N に設定されている場合、 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> は <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 5 (または N/5) で割った値に設定され、 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> はプロパティの値の5倍 ( <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> または 5n) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7de25-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="7de25-110">遅延を設定するには</span><span class="sxs-lookup"><span data-stu-id="7de25-110">To set the delay</span></span>  
  
1. <span data-ttu-id="7de25-111">この例に示すように、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7de25-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7de25-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7de25-112">See also</span></span>

- [<span data-ttu-id="7de25-113">ToolTip コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="7de25-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="7de25-114">方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する</span><span class="sxs-lookup"><span data-stu-id="7de25-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="7de25-115">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7de25-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
