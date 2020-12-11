---
title: SaveFileDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974386"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="f8961-102">SaveFileDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="f8961-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="f8961-103">Windows フォームの <xref:System.Windows.Forms.SaveFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="f8961-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="f8961-104">これは、Windows によって使用される標準の [ **ファイルの保存** ] ダイアログボックスと同じです。</span><span class="sxs-lookup"><span data-stu-id="f8961-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="f8961-105">これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。</span><span class="sxs-lookup"><span data-stu-id="f8961-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="f8961-106">SaveFileDialog コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="f8961-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="f8961-107">独自のダイアログボックスを構成する代わりに、ユーザーがファイルを保存できるようにするための簡単なソリューションとして使用します。</span><span class="sxs-lookup"><span data-stu-id="f8961-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="f8961-108">標準の Windows ダイアログボックスに依存しているため、ユーザーにとって作成するアプリケーションの基本的な機能はすぐにわかります。</span><span class="sxs-lookup"><span data-stu-id="f8961-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="f8961-109">ただし、コンポーネントを使用する場合は、 <xref:System.Windows.Forms.SaveFileDialog> 独自のファイル保存ロジックを作成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8961-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="f8961-110">メソッドを使用し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> て、実行時にダイアログボックスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f8961-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="f8961-111">メソッドを使用して、読み取り/書き込みモードでファイルを開くことができ <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f8961-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="f8961-112">フォームに追加されると、 <xref:System.Windows.Forms.SaveFileDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8961-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8961-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8961-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="f8961-114">SaveFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f8961-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
