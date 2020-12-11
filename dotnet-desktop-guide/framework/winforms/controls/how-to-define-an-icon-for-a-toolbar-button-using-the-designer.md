---
title: '方法: デザイナーを使って ToolBar ボタンのアイコンを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980876"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>方法: デザイナーを使って ToolBar ボタンのアイコンを定義する

> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。

<xref:System.Windows.Forms.ToolBar> ボタンは、ユーザーが簡単に識別できるように、それらの中にアイコンを表示できます。 これは、コンポーネントにイメージを追加 <xref:System.Windows.Forms.ImageList> し、コントロールに関連付けることによって実現され <xref:System.Windows.Forms.ToolBar> ます。

次の手順では、コントロールとコンポーネントを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ImageList> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>デザイン時にツールバーボタンのアイコンを設定するには

1. コンポーネントにイメージを追加 <xref:System.Windows.Forms.ImageList> します。 詳細については、「 [方法: デザイナーを使用して ImageList イメージを追加または削除する](how-to-add-or-remove-imagelist-images-with-the-designer.md)」を参照してください。

2. <xref:System.Windows.Forms.ToolBar>フォーム上のコントロールを選択します。

3. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.ToolBar> コントロールの <xref:System.Windows.Forms.ToolBar.ImageList%2A> プロパティをコンポーネントに設定し <xref:System.Windows.Forms.ImageList> ます。

4. <xref:System.Windows.Forms.ToolBar>コントロールのプロパティをクリックし <xref:System.Windows.Forms.ToolBar.Buttons%2A> て選択し、省略記号 ([ ![ Visual Studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして ](./media/visual-studio-ellipsis-button.png) **ToolBarButton Collection エディター** を開きます。

5. コントロールにボタンを追加するには、[ **追加** ] ボタンを使用し <xref:System.Windows.Forms.ToolBar> ます。

6. **ToolBarButton Collection エディター** の右側にあるペインに表示される [**プロパティ**] ウィンドウで、 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 各ツールバーボタンのプロパティを、コンポーネントに追加したイメージから描画されるリスト内の値のいずれかに設定し <xref:System.Windows.Forms.ImageList> ます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolBar>
- [方法: ツール バー ボタンのメニュー イベントをトリガーする](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar コントロール](toolbar-control-windows-forms.md)
- [ImageList コンポーネント](imagelist-component-windows-forms.md)
