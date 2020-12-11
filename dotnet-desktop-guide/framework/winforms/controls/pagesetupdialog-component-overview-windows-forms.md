---
title: PageSetupDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982888"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="10780-102">PageSetupDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="10780-102">PageSetupDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="10780-103">Windows フォーム <xref:System.Windows.Forms.PageSetupDialog> コンポーネントは、Windows ベースのアプリケーションで印刷するページの詳細を設定するために使用する、事前に構成されたダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="10780-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="10780-104">ユーザーが独自のダイアログボックスを構成する代わりにページ設定を設定するための簡単なソリューションとして、Windows ベースのアプリケーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="10780-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="10780-105">ユーザーが罫線と余白の調整、ヘッダーとフッター、縦または横の向きを設定できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10780-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="10780-106">Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10780-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="10780-107">キーのプロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="10780-107">Key Properties and Methods</span></span>

<span data-ttu-id="10780-108">実行時 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> にダイアログを表示するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="10780-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="10780-109">このコンポーネントには、1つのページ ( <xref:System.Drawing.Printing.PrintDocument> クラス) または任意のドキュメント (クラス) に関連する設定可能なプロパティがあり <xref:System.Drawing.Printing.PageSettings> ます。</span><span class="sxs-lookup"><span data-stu-id="10780-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="10780-110">また、コンポーネントを使用して、 <xref:System.Windows.Forms.PageSetupDialog> クラスに格納されている特定のプリンター設定を決定することもでき <xref:System.Drawing.Printing.PrinterSettings> ます。</span><span class="sxs-lookup"><span data-stu-id="10780-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>

<span data-ttu-id="10780-111">フォームに追加されると、 <xref:System.Windows.Forms.PageSetupDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10780-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="10780-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="10780-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="10780-113">PageSetupDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10780-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
