---
title: PrintDialog コンポーネントを表示する方法
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980827"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="0cb43-102">PrintDialog コンポーネントを表示する方法</span><span class="sxs-lookup"><span data-stu-id="0cb43-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="0cb43-103"><xref:System.Windows.Forms.PrintDialog>コンポーネントは、ユーザーの多くが使い慣れている標準の Windows 印刷ダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="0cb43-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="0cb43-104">ユーザーはすぐに使いやすくなるため、コンポーネントを使用すると便利 <xref:System.Windows.Forms.PrintDialog> です。</span><span class="sxs-lookup"><span data-stu-id="0cb43-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="0cb43-105">PrintDialog コンポーネントを表示するには</span><span class="sxs-lookup"><span data-stu-id="0cb43-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="0cb43-106"><xref:System.Windows.Forms.Form.ShowDialog%2A>アプリケーションのコード内からメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0cb43-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="0cb43-107">コンポーネントが表示されると、ユーザーはそれを使用して印刷ジョブのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0cb43-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="0cb43-108">これらは、  <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> その印刷ジョブに関連付けられているクラス (およびユーザーがコンポーネントを介して [PageSetupDialog コンポーネント](pagesetupdialog-component-windows-forms.md) にアクセスする場合はクラス) に保存され <xref:System.Windows.Forms.PrintDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="0cb43-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="0cb43-109">その後で、設定されたプロパティを呼び出して印刷ジョブの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0cb43-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cb43-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cb43-110">See also</span></span>

- [<span data-ttu-id="0cb43-111">方法: 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="0cb43-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="0cb43-112">方法: 実行時に PrintDialog のユーザー入力をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="0cb43-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="0cb43-113">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="0cb43-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="0cb43-114">PrintDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0cb43-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="0cb43-115">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="0cb43-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="0cb43-116">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="0cb43-116">Windows Forms Controls</span></span>](index.md)
