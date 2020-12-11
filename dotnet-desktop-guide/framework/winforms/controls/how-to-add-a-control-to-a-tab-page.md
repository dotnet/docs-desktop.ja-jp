---
title: '方法: タブ ページにコントロールを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 9806583fda60f1cb8a5ef2d97f42eba158593f61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981020"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>方法: タブ ページにコントロールを追加する
Windows フォームを使用すると、 <xref:System.Windows.Forms.TabControl> 他のコントロールを整理して表示できます。 次の手順は、最初のタブにボタンを追加する方法を示しています。タブページのラベル部分にアイコンを追加する方法の詳細については、「 [方法: Windows フォーム TabControl の外観を変更する](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)」を参照してください。  
  
### <a name="to-add-a-control-programmatically"></a>プログラムによってコントロールを追加するには  
  
1. <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>のプロパティによって返されるコレクションのメソッドを使用し <xref:System.Windows.Forms.Control.Controls%2A> <xref:System.Windows.Forms.TabPage> ます。  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>関連項目

- [TabControl コントロール](tabcontrol-control-windows-forms.md)
- [TabControl コントロールの概要](tabcontrol-control-overview-windows-forms.md)
- [方法: Windows フォーム TabControl の表示形式を変更する](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [方法: タブ ページを無効化する](how-to-disable-tab-pages.md)
- [方法: Windows フォーム TabControl のタブを追加および削除する](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
