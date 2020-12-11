---
title: '方法: ToolStrip コントロールにトグル ボタンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982175"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>方法: ToolStrip コントロールにトグル ボタンを作成する

ユーザーがトグルボタンをクリックすると、くぼんで表示され、ユーザーがボタンを再度クリックするまで、くぼんだ外観を保持します。

## <a name="to-create-a-toggling-toolstripbutton"></a>切り替え ToolStripButton を作成するには

- 次のコード例のようなコードを使用します。 このコードは、フォームにコントロールが含まれて <xref:System.Windows.Forms.ToolStrip> おり、そのコレクションにが呼び出されたが含まれていることを前提としてい <xref:System.Windows.Forms.ToolStrip.Items%2A> <xref:System.Windows.Forms.ToolStripButton> `toolStripButton1` ます。 また、というイベントハンドラーがあることを前提としてい `toolStripButton1_CheckedChanged` ます。

    ```vb
    toolStripButton1.CheckOnClick = True
    toolStripButton1.CheckedChanged AddressOf _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

    ```csharp
    toolStripButton1.CheckOnClick = true;
    toolStripButton1.CheckedChanged += new _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStripButton>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
