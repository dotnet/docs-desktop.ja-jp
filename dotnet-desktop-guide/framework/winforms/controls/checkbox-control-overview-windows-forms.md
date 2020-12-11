---
title: CheckBox コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975105"
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="95aac-102">CheckBox コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="95aac-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="95aac-103">Windows フォーム <xref:System.Windows.Forms.CheckBox> コントロールは、特定の条件がオンかオフかを示します。</span><span class="sxs-lookup"><span data-stu-id="95aac-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="95aac-104">一般的に、はい/いいえ、または True/False の選択肢をユーザーに提示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="95aac-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="95aac-105">ユーザーが 1 つ以上選択可能な複数の選択肢を表示するために、チェック ボックス コントロールをグループの中で使用できます。</span><span class="sxs-lookup"><span data-stu-id="95aac-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="95aac-106">チェックボックスコントロールは、ユーザーが選択した項目を示すために使用されるという点で、オプションボタンコントロールに似ています。</span><span class="sxs-lookup"><span data-stu-id="95aac-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="95aac-107">グループ内のラジオボタンは一度に1つしか選択できないという点で異なります。</span><span class="sxs-lookup"><span data-stu-id="95aac-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="95aac-108">ただし、チェックボックスコントロールを使用すると、任意の数のチェックボックスをオンにできます。</span><span class="sxs-lookup"><span data-stu-id="95aac-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="95aac-109">チェックボックスは、単純なデータバインディングを使用してデータベース内の要素に接続されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="95aac-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="95aac-110">複数のチェックボックスは、コントロールを使用してグループ化することができ <xref:System.Windows.Forms.GroupBox> ます。</span><span class="sxs-lookup"><span data-stu-id="95aac-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="95aac-111">これは、視覚的な外観やユーザーインターフェイスのデザインに役立ちます。グループ化されたコントロールはフォームデザイナー上で一緒に移動できるためです。</span><span class="sxs-lookup"><span data-stu-id="95aac-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="95aac-112">詳細については、「 [データバインディング](../windows-forms-data-binding.md) と [GroupBox コントロール](groupbox-control-windows-forms.md)の Windows フォーム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95aac-112">For more information, see [Windows Forms Data Binding](../windows-forms-data-binding.md) and [GroupBox Control](groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="95aac-113"><xref:System.Windows.Forms.CheckBox>コントロールには、とという2つの重要なプロパティがあり <xref:System.Windows.Forms.CheckBox.Checked%2A> <xref:System.Windows.Forms.CheckBox.CheckState%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="95aac-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="95aac-114">プロパティは、 <xref:System.Windows.Forms.CheckBox.Checked%2A> またはのいずれかを返し `true` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="95aac-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="95aac-115">プロパティは、またはの <xref:System.Windows.Forms.CheckBox.CheckState%2A> いずれかを返します <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Unchecked> 。または、 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> プロパティがに設定されている場合、 `true` もを <xref:System.Windows.Forms.CheckBox.CheckState%2A> 返すことがあり <xref:System.Windows.Forms.CheckState.Indeterminate> ます。</span><span class="sxs-lookup"><span data-stu-id="95aac-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="95aac-116">不確定状態では、オプションが使用できないことを示す淡色表示のボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95aac-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95aac-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="95aac-117">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="95aac-118">方法 : Windows フォームの CheckBox コントロールでオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="95aac-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="95aac-119">方法 : Windows フォーム CheckBox のクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="95aac-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="95aac-120">CheckBox コントロール</span><span class="sxs-lookup"><span data-stu-id="95aac-120">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
