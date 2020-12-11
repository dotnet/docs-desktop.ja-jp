---
title: FontDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974154"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="b84b8-102">FontDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="b84b8-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b84b8-103">Windows フォームコンポーネントは、事前に構成された <xref:System.Windows.Forms.FontDialog> ダイアログボックスです。これは、システムに現在インストールされているフォントを公開するために使用される標準の Windows **フォント** ダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="b84b8-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="b84b8-104">独自のダイアログボックスを構成する代わりに、フォントを選択するための簡単なソリューションとして、Windows ベースのアプリケーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="b84b8-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="b84b8-105">既定では、ダイアログボックスには、フォント、フォントスタイル、およびサイズのリストボックスが表示されます。取り消し線や下線などの効果のチェックボックススクリプトのドロップダウンリストフォントの表示方法を示すサンプルがあります。</span><span class="sxs-lookup"><span data-stu-id="b84b8-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="b84b8-106">(スクリプトは、ヘブライ語や日本語など、特定のフォントで使用できるさまざまな文字スクリプトを参照します。)[フォント] ダイアログボックスを表示するには、メソッドを呼び出し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b84b8-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b84b8-107">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="b84b8-107">Key Properties</span></span>  
 <span data-ttu-id="b84b8-108">コンポーネントには、その外観を構成する多数のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b84b8-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="b84b8-109">ダイアログボックスの選択項目を設定するプロパティは、 <xref:System.Windows.Forms.FontDialog.Font%2A> と <xref:System.Windows.Forms.FontDialog.Color%2A> です。</span><span class="sxs-lookup"><span data-stu-id="b84b8-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="b84b8-110">プロパティは、 <xref:System.Windows.Forms.FontDialog.Font%2A> フォント、スタイル、サイズ、スクリプト、および効果を設定します。たとえば、のようにし `Arial, 10pt, style=Italic, Strikeout` ます。</span><span class="sxs-lookup"><span data-stu-id="b84b8-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84b8-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b84b8-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="b84b8-112">FontDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b84b8-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
