---
title: DataGridView コントロールの編集モードを指定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982803"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>方法: Windows フォーム DataGridView コントロールの編集モードを指定する
既定では、ユーザーは、現在の <xref:System.Windows.Forms.DataGridView> テキストボックスのセルを入力するか、F2 キーを押すことで、その内容を編集できます。 これにより、次のすべての条件が満たされた場合にセルが編集モードになります。  
  
- 基になるデータソースは編集をサポートしています。  
  
- <xref:System.Windows.Forms.DataGridView>コントロールが有効になっています。  
  
- <xref:System.Windows.Forms.DataGridView.EditMode%2A> プロパティ値が <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically> ではない。  
  
- `ReadOnly`セル、行、列、およびコントロールのプロパティはすべてに設定されてい `false` ます。  
  
 編集モードでは、ユーザーはセルの値を変更し、ENTER キーを押して変更をコミットするか、ESC キーを押してセルを元の値に戻すことができます。  
  
 <xref:System.Windows.Forms.DataGridView>セルが現在のセルになるとすぐに編集モードに切り替わるように、コントロールを構成できます。 この場合、ENTER キーと ESC キーの動作は変更されませんが、値がコミットまたは元に戻されると、セルは編集モードのままになります。 また、ユーザーがセルを入力したとき、またはユーザーが F2 キーを押したときにのみ、セルが編集モードになるように、コントロールを構成することもできます。 最後に、メソッドを呼び出す場合を除き、セルが編集モードに入ってしまうのを防ぐことができます <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 。  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>DataGridView コントロールの編集モードを変更するには  
  
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>プロパティを適切な列挙値に設定し <xref:System.Windows.Forms.DataGridViewEditMode> ます。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
- <xref:System> アセンブリおよび <xref:System.Windows.Forms> アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでのデータ入力](data-entry-in-the-windows-forms-datagridview-control.md)
