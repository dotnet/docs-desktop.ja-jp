---
title: MonthCalendar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982924"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>MonthCalendar コントロールの概要 (Windows フォーム)
Windows フォームコントロールは、 <xref:System.Windows.Forms.MonthCalendar> ユーザーが日付情報を表示および設定するための直感的なグラフィカルインターフェイスを提供します。 このコントロールには、カレンダーが表示されます。このグリッドには、月の日付を含むグリッドが表示されます。選択した日付範囲が強調表示されます。 月のキャプションの両側にある矢印ボタンをクリックすると、別の月を選択できます。 同様のコントロールとは異なり <xref:System.Windows.Forms.DateTimePicker> 、このコントロールでは複数の日付を選択できます。 コントロールの詳細については <xref:System.Windows.Forms.DateTimePicker> 、「 [DateTimePicker control](datetimepicker-control-windows-forms.md)」を参照してください。  
  
## <a name="configuring-the-monthcalendar-control"></a>MonthCalendar コントロールの構成  
 <xref:System.Windows.Forms.MonthCalendar>コントロールの外観は、高度な構成が可能です。 既定では、今日の日付は丸で囲まれて表示され、グリッドの下部にも示されます。 この機能を変更するには、 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> プロパティとプロパティをに設定し `false` ます。 また、プロパティをに設定することによって、週番号をカレンダーに追加することもでき <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> `true` ます。 プロパティを設定することにより <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 、複数の月を水平方向および垂直方向に表示できます。 既定では、日曜日は週の最初の曜日として表示されますが、プロパティを使用して任意の日を指定でき <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> ます。  
  
 また、 <xref:System.DateTime> 、、およびの各プロパティにオブジェクトを追加することによって、特定の日付を1回だけ、または月単位で太字で表示するように設定することもでき <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> ます。 詳細については、「 [方法: Windows フォーム MonthCalendar コントロールを使用して特定の日付を太字で表示する](display-specific-days-in-bold-with-wf-monthcalendar-control.md)」を参照してください。  
  
 コントロールのキープロパティ <xref:System.Windows.Forms.MonthCalendar> は <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 、コントロールで選択された日付の範囲です。 この <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 値は、プロパティで設定できる最大日数を超えることはできません <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> 。 ユーザーが選択できる最も古い日付と最新の日付は、 <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> プロパティとプロパティによって決まり <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar コントロール](monthcalendar-control-windows-forms.md)
