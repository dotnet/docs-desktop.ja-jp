---
title: MonthCalendar コントロールで日付の範囲を選択する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: bda96af21a8f86a54d5c0fe0204546b980076d26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980712"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="02b93-102">方法 : Windows フォームの MonthCalendar コントロールで日付の範囲を選択する</span><span class="sxs-lookup"><span data-stu-id="02b93-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="02b93-103">Windows フォームコントロールの重要な機能 <xref:System.Windows.Forms.MonthCalendar> は、ユーザーが日付の範囲を選択できることです。</span><span class="sxs-lookup"><span data-stu-id="02b93-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="02b93-104">この機能は、 <xref:System.Windows.Forms.DateTimePicker> ユーザーが単一の日付/時刻値を選択できるようにするコントロールの日付選択機能を改善したものです。</span><span class="sxs-lookup"><span data-stu-id="02b93-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="02b93-105">コントロールのプロパティを使用して、日付の範囲を設定したり、ユーザーが設定した範囲を取得したりでき <xref:System.Windows.Forms.MonthCalendar> ます。</span><span class="sxs-lookup"><span data-stu-id="02b93-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="02b93-106">次のコード例は、選択範囲を設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="02b93-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="02b93-107">日付の範囲を選択するには</span><span class="sxs-lookup"><span data-stu-id="02b93-107">To select a range of dates</span></span>  
  
1. <span data-ttu-id="02b93-108"><xref:System.DateTime>範囲内の最初と最後の日付を表すオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="02b93-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2. <span data-ttu-id="02b93-109"><xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="02b93-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     <span data-ttu-id="02b93-110">\- または -</span><span class="sxs-lookup"><span data-stu-id="02b93-110">–or–</span></span>  
  
     <span data-ttu-id="02b93-111"><xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> と <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="02b93-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="02b93-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="02b93-112">See also</span></span>

- [<span data-ttu-id="02b93-113">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="02b93-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="02b93-114">方法 : Windows フォームの MonthCalendar コントロールの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="02b93-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="02b93-115">方法 : Windows フォームの MonthCalendar コントロールを使用して特定の日付を太字で表示する</span><span class="sxs-lookup"><span data-stu-id="02b93-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="02b93-116">方法 : Windows フォームの MonthCalendar コントロールにおいて複数の月を表示する</span><span class="sxs-lookup"><span data-stu-id="02b93-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
