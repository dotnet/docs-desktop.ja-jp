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
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="7ed81-102">方法: ToolStrip コントロールにトグル ボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="7ed81-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>

<span data-ttu-id="7ed81-103">ユーザーがトグルボタンをクリックすると、くぼんで表示され、ユーザーがボタンを再度クリックするまで、くぼんだ外観を保持します。</span><span class="sxs-lookup"><span data-stu-id="7ed81-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>

## <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="7ed81-104">切り替え ToolStripButton を作成するには</span><span class="sxs-lookup"><span data-stu-id="7ed81-104">To create a toggling ToolStripButton</span></span>

- <span data-ttu-id="7ed81-105">次のコード例のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ed81-105">Use code such as the following code example.</span></span> <span data-ttu-id="7ed81-106">このコードは、フォームにコントロールが含まれて <xref:System.Windows.Forms.ToolStrip> おり、そのコレクションにが呼び出されたが含まれていることを前提としてい <xref:System.Windows.Forms.ToolStrip.Items%2A> <xref:System.Windows.Forms.ToolStripButton> `toolStripButton1` ます。</span><span class="sxs-lookup"><span data-stu-id="7ed81-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="7ed81-107">また、というイベントハンドラーがあることを前提としてい `toolStripButton1_CheckedChanged` ます。</span><span class="sxs-lookup"><span data-stu-id="7ed81-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7ed81-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ed81-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="7ed81-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7ed81-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
