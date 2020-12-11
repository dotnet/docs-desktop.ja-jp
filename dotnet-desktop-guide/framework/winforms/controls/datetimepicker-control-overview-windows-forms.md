---
title: DateTimePicker コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 63271dd91116c1f68d426f3ed5aa710644ded928
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974207"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>DateTimePicker コントロールの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.DateTimePicker> コントロールを使用すると、ユーザーは日付または時刻の一覧から1つの項目を選択できます。 日付を表すために使用した場合、2つの部分に表示されます。テキストで日付が表示されたドロップダウンリストと、一覧の横にある下向き矢印をクリックしたときに表示されるグリッドです。 グリッドは、複数の <xref:System.Windows.Forms.MonthCalendar> 日付を選択するために使用できるコントロールに似ています。 コントロールの詳細につい <xref:System.Windows.Forms.MonthCalendar> ては、「 [MonthCalendar Control の概要](monthcalendar-control-overview-windows-forms.md)」を参照してください。  
  
## <a name="key-properties"></a>キー プロパティ  
 <xref:System.Windows.Forms.DateTimePicker>を日付ではなく、選択した時間のコントロールとして表示する場合は、プロパティをに設定し、 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> `true` <xref:System.Windows.Forms.DateTimePicker.Format%2A> プロパティをに設定し <xref:System.Windows.Forms.DateTimePickerFormat.Time> ます。 詳細について [は、「方法: DateTimePicker コントロールを使用して時刻を表示する](how-to-display-time-with-the-datetimepicker-control.md)」を参照してください。  
  
 プロパティがに設定されている場合 <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> `true` 、コントロールで選択された日付の横にチェックボックスが表示されます。 チェックボックスをオンにすると、選択した日付/時刻値を更新できます。 このチェックボックスが空の場合、値は使用できません。  
  
 コントロールのプロパティとプロパティによって、 <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> 日付と時刻の範囲が決まります。 プロパティは、 <xref:System.Windows.Forms.DateTimePicker.Value%2A> コントロールが設定されている現在の日付と時刻を格納します。 詳細については、「 [方法: Windows フォーム DateTimePicker コントロールを使用して日付を設定して返す](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)」を参照してください。 値は <xref:System.Windows.Forms.DateTimePicker.Format%2A> <xref:System.Windows.Forms.DateTimePickerFormat.Long> 、プロパティ (、、 <xref:System.Windows.Forms.DateTimePickerFormat.Short> <xref:System.Windows.Forms.DateTimePickerFormat.Time> 、または <xref:System.Windows.Forms.DateTimePickerFormat.Custom> ) によって設定される4つの形式で表示できます。 カスタム書式が選択されている場合は、 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> プロパティを適切な文字列に設定する必要があります。 詳細については、「 [方法: Windows フォーム DateTimePicker コントロールを使用してカスタム書式で日付を表示する](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [方法: Windows フォームの DateTimePicker コントロールを使用してカスタム形式で日付を表示する](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [方法: Windows フォームの DateTimePicker コントロールを使用して日付を設定および取得する](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
