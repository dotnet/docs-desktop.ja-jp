---
title: MonthCalendar コントロールを使用して特定の日を太字で表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981551"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="5da17-102">方法 : Windows フォームの MonthCalendar コントロールを使用して特定の日付を太字で表示する</span><span class="sxs-lookup"><span data-stu-id="5da17-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="5da17-103">Windows フォーム <xref:System.Windows.Forms.MonthCalendar> コントロールでは、単数形または繰り返しのいずれかの形式で、日付を太字で表示できます。</span><span class="sxs-lookup"><span data-stu-id="5da17-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="5da17-104">これは、休日や週末など、特別な日付に注意を引くために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5da17-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="5da17-105">この機能は、3つのプロパティによって制御できます。</span><span class="sxs-lookup"><span data-stu-id="5da17-105">Three properties control this feature.</span></span> <span data-ttu-id="5da17-106">プロパティには、 <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 1 つの日付が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5da17-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="5da17-107">プロパティには、 <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 毎年太字で表示される日付が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5da17-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="5da17-108">プロパティには、 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 毎月太字で表示される日付が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5da17-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="5da17-109">これらの各プロパティには、オブジェクトの配列が含まれてい <xref:System.DateTime> ます。</span><span class="sxs-lookup"><span data-stu-id="5da17-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="5da17-110">これらの一覧のいずれかから日付を追加または削除するには、オブジェクトを追加または削除する必要があり <xref:System.DateTime> ます。</span><span class="sxs-lookup"><span data-stu-id="5da17-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="5da17-111">日付を太字で表示するには</span><span class="sxs-lookup"><span data-stu-id="5da17-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="5da17-112">オブジェクトを作成 <xref:System.DateTime> します。</span><span class="sxs-lookup"><span data-stu-id="5da17-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. <span data-ttu-id="5da17-113"><xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A> <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A> コントロールの、、またはメソッドを呼び出して、1つの日付を太字にし <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> <xref:System.Windows.Forms.MonthCalendar> ます。</span><span class="sxs-lookup"><span data-stu-id="5da17-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="5da17-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="5da17-114">–or–</span></span>  
  
     <span data-ttu-id="5da17-115">一連の日付を一度に太字にするには、オブジェクトの配列を作成 <xref:System.DateTime> して、いずれかのプロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5da17-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="5da17-116">標準フォントで日付を表示するには</span><span class="sxs-lookup"><span data-stu-id="5da17-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="5da17-117"><xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>、 <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A> 、またはメソッドを呼び出して、1つの太字の日付を通常のフォントで表示し <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5da17-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="5da17-118">\- または -</span><span class="sxs-lookup"><span data-stu-id="5da17-118">–or–</span></span>  
  
     <span data-ttu-id="5da17-119"><xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>、 <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A> 、またはメソッドを呼び出して、3つのリストのいずれかから太字で表示されているすべての日付を削除し <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5da17-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="5da17-120">メソッドを呼び出して、フォントの外観を更新し <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5da17-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5da17-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="5da17-121">See also</span></span>

- [<span data-ttu-id="5da17-122">MonthCalendar コントロール</span><span class="sxs-lookup"><span data-stu-id="5da17-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="5da17-123">方法 : Windows フォームの MonthCalendar コントロールで日付の範囲を選択する</span><span class="sxs-lookup"><span data-stu-id="5da17-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="5da17-124">方法 : Windows フォームの MonthCalendar コントロールの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="5da17-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="5da17-125">方法 : Windows フォームの MonthCalendar コントロールにおいて複数の月を表示する</span><span class="sxs-lookup"><span data-stu-id="5da17-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
