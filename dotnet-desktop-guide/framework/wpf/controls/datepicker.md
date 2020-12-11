---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 4e4b536aca768872a0729a9b34a5dc1cc17e04fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984460"
---
# <a name="datepicker"></a><span data-ttu-id="92dbd-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="92dbd-102">DatePicker</span></span>
<span data-ttu-id="92dbd-103"><xref:System.Windows.Controls.DatePicker> コントロールを使用すると、ユーザーは、テキスト フィールドに入力するか、ドロップダウン <xref:System.Windows.Controls.Calendar> コントロールを使用して、日付を選択できます。</span><span class="sxs-lookup"><span data-stu-id="92dbd-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="92dbd-104">次の図は、<xref:System.Windows.Controls.DatePicker> を示しています。</span><span class="sxs-lookup"><span data-stu-id="92dbd-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="92dbd-105">![DatePicker コントロール](./media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="92dbd-105">![DatePicker control](./media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="92dbd-106">DatePicker コントロール</span><span class="sxs-lookup"><span data-stu-id="92dbd-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="92dbd-107"><xref:System.Windows.Controls.DatePicker> コントロールのプロパティの多くは、その組み込みの <xref:System.Windows.Controls.Calendar> を管理するためのものであり、<xref:System.Windows.Controls.Calendar> の同等のプロパティと同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="92dbd-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="92dbd-108">特に、<xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> の各プロパティは、対応する <xref:System.Windows.Controls.Calendar> の各プロパティと同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="92dbd-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="92dbd-109">詳細については、「<xref:System.Windows.Controls.Calendar>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92dbd-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="92dbd-110">ユーザーは、テキスト フィールドに日付を直接入力できます。これにより、<xref:System.Windows.Controls.DatePicker.Text%2A> プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="92dbd-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="92dbd-111"><xref:System.Windows.Controls.DatePicker> が、入力した文字列を有効な日付に変換できない場合は、<xref:System.Windows.Controls.DatePicker.DateValidationError> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="92dbd-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="92dbd-112">既定では、これが例外の原因となりますが、<xref:System.Windows.Controls.DatePicker.DateValidationError> のイベント ハンドラーにより <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> プロパティが `false` に設定されることで、例外の発生を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="92dbd-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dbd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="92dbd-113">See also</span></span>

- [<span data-ttu-id="92dbd-114">コントロール</span><span class="sxs-lookup"><span data-stu-id="92dbd-114">Controls</span></span>](index.md)
- [<span data-ttu-id="92dbd-115">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="92dbd-115">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
