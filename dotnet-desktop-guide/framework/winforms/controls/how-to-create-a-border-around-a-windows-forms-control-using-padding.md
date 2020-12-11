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
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>方法: 埋め込みを使用して Windows フォーム コントロールの周囲に境界線を作成する
次のコード例は、境界線を作成する方法、またはコントロールの周囲をアウトラインする方法を示して <xref:System.Windows.Forms.RichTextBox> います。 この例では、 <xref:System.Windows.Forms.Panel> コントロールのプロパティの値を <xref:System.Windows.Forms.Padding> 5 に設定し、 <xref:System.Windows.Forms.Control.Dock%2A> 子コントロールのプロパティ <xref:System.Windows.Forms.RichTextBox> をに設定し <xref:System.Windows.Forms.DockStyle.Fill> ます。 <xref:System.Windows.Forms.Control.BackColor%2A>コントロールのが <xref:System.Windows.Forms.Panel> に設定され <xref:System.Drawing.Color.Blue%2A> ます。これにより、コントロールの周囲に青い境界線が作成され <xref:System.Windows.Forms.RichTextBox> ます。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Padding>
- [Windows フォーム コントロールでのマージンと埋め込み](margin-and-padding-in-windows-forms-controls.md)
