---
title: '方法: プロフェッショナル スタイルの ToolStrip コントロールを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982191"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="83c47-102">方法: プロフェッショナル スタイルの ToolStrip コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="83c47-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="83c47-103"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> 型から派生する独自のクラスを記述することで、アプリケーションの <xref:System.Windows.Forms.ToolStrip> コントロールにプロフェッショナルな外観と動作 (操作性) を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="83c47-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="83c47-104">この機能は Visual Studio で幅広くサポートされています。</span><span class="sxs-lookup"><span data-stu-id="83c47-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="83c47-105">「[チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成](walkthrough-creating-a-professionally-styled-toolstrip-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83c47-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c47-106">例</span><span class="sxs-lookup"><span data-stu-id="83c47-106">Example</span></span>  
 <span data-ttu-id="83c47-107">次のコード例は、コントロールを使用して、 <xref:System.Windows.Forms.ToolStrip> Microsoft® Outlook®によって提供される **ナビゲーションウィンドウ** に似た複合コントロールを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="83c47-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83c47-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="83c47-108">Compiling the Code</span></span>  
 <span data-ttu-id="83c47-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="83c47-109">This example requires:</span></span>  
  
- <span data-ttu-id="83c47-110">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="83c47-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c47-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="83c47-111">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="83c47-112">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="83c47-112">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="83c47-113">方法: フォームに標準メニュー項目を追加する</span><span class="sxs-lookup"><span data-stu-id="83c47-113">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
