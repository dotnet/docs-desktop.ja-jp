---
title: '方法: ToolStrip を ToolStripContainer からフォームに移動する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: c6519add6789485d41146633abb5e11f80913649
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980759"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>方法: ToolStrip を ToolStripContainer からフォームに移動する
をフォームに移動するには、次の手順に従い <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripContainer> ます。

## <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>ToolStrip を ToolStripContainer からフォームに移動するには

1. <xref:System.Windows.Forms.ToolStrip>を選択します。

2. CTRL キーを <xref:System.Windows.Forms.ToolStrip> 押しながら X キーを押してを切り取るか、を右クリック <xref:System.Windows.Forms.ToolStrip> してコンテキストメニューの [ **切り取り** ] を選択します。

3. フォームを選択します。

4. <xref:System.Windows.Forms.ToolStrip>CTRL キーを押しながら V キーを押すか、[**編集**] メニューの [**貼り付け**] をクリックして、を貼り付けます。

5. の <xref:System.Windows.Forms.ToolStrip.Dock%2A> プロパティを <xref:System.Windows.Forms.ToolStrip> **Top** に設定します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
