---
title: パディングを使用してコントロールの周囲に罫線を作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982199"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="78fe4-102">方法: 埋め込みを使用して Windows フォーム コントロールの周囲に境界線を作成する</span><span class="sxs-lookup"><span data-stu-id="78fe4-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="78fe4-103">次のコード例は、境界線を作成する方法、またはコントロールの周囲をアウトラインする方法を示して <xref:System.Windows.Forms.RichTextBox> います。</span><span class="sxs-lookup"><span data-stu-id="78fe4-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="78fe4-104">この例では、 <xref:System.Windows.Forms.Panel> コントロールのプロパティの値を <xref:System.Windows.Forms.Padding> 5 に設定し、 <xref:System.Windows.Forms.Control.Dock%2A> 子コントロールのプロパティ <xref:System.Windows.Forms.RichTextBox> をに設定し <xref:System.Windows.Forms.DockStyle.Fill> ます。</span><span class="sxs-lookup"><span data-stu-id="78fe4-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="78fe4-105"><xref:System.Windows.Forms.Control.BackColor%2A>コントロールのが <xref:System.Windows.Forms.Panel> に設定され <xref:System.Drawing.Color.Blue%2A> ます。これにより、コントロールの周囲に青い境界線が作成され <xref:System.Windows.Forms.RichTextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="78fe4-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78fe4-106">例</span><span class="sxs-lookup"><span data-stu-id="78fe4-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="78fe4-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="78fe4-107">See also</span></span>

- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="78fe4-108">Windows フォーム コントロールでのマージンと埋め込み</span><span class="sxs-lookup"><span data-stu-id="78fe4-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)
