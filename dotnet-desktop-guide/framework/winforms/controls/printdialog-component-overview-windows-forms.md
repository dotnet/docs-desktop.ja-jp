---
title: PrintDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980563"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="1fc4f-102">PrintDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="1fc4f-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="1fc4f-103">Windows フォーム [PrintDialog](printdialog-component-windows-forms.md) コンポーネントは、プリンターの選択、印刷するページの選択、および Windows ベースのアプリケーションでのその他の印刷関連設定の決定に使用される、事前に構成されたダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="1fc4f-104">独自のダイアログ ボックスを構成する代わりに、プリンターと印刷関連の設定の選択のための簡単なソリューションとして使用します。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="1fc4f-105">ユーザーがドキュメントのさまざまな部分を印刷できるようにするには、[すべて印刷]、選択したページ範囲を印刷する、または選択内容を印刷します。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="1fc4f-106">Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="1fc4f-107"><xref:System.Windows.Forms.PrintDialog>コンポーネントはクラスから継承され <xref:System.Windows.Forms.CommonDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="1fc4f-108">コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="1fc4f-108">Working with the Component</span></span>

<span data-ttu-id="1fc4f-109">実行時 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> にダイアログボックスを表示するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="1fc4f-110">このコンポーネントには、1つの印刷ジョブ ( <xref:System.Drawing.Printing.PrintDocument> クラス) または個々のプリンターの設定 (クラス) に関連するプロパティがあり <xref:System.Drawing.Printing.PrinterSettings> ます。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="1fc4f-111">これらはいずれも、複数のプリンターで共有できます。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="1fc4f-112">フォームに追加されると、 <xref:System.Windows.Forms.PrintDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fc4f-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fc4f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fc4f-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="1fc4f-114">PrintDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1fc4f-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
