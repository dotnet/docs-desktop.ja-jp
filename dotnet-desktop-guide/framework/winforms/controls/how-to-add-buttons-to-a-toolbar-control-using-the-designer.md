---
title: '方法: デザイナーを使って ToolBar コントロールにボタンを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981007"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>方法: デザイナーを使って ToolBar コントロールにボタンを追加する

> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。

コントロールの不可欠な部分 <xref:System.Windows.Forms.ToolBar> は、コントロールに追加するボタンです。 これらは、メニューコマンドに簡単にアクセスできるようにするために使用できます。また、アプリケーションのユーザーインターフェイスの別の領域に配置して、メニュー構造では使用できないコマンドをユーザーに公開することもできます。

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ToolBar> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

### <a name="to-add-buttons-at-design-time"></a>デザイン時にボタンを追加するには

1. <xref:System.Windows.Forms.ToolBar> コントロールを選択します。

2. [ **プロパティ** ] ウィンドウで、プロパティをクリックして選択し、 <xref:System.Windows.Forms.ToolBar.Buttons%2A> **省略記号** ([ ![ Visual Studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして ](./media/visual-studio-ellipsis-button.png) **ToolBarButton Collection エディター** を開きます。

3. コントロールのボタンを追加および削除するには、[ **追加** ] ボタンと [ **削除** ] ボタンを使用し <xref:System.Windows.Forms.ToolBar> ます。

4. エディターの右側のペインに表示される [ **プロパティ** ] ウィンドウで、個々のボタンのプロパティを構成します。 次の表は、考慮する必要があるいくつかの重要なプロパティを示しています。

    |プロパティ|説明|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|ドロップダウンツールバーボタンに表示するメニューを設定します。 ツールバーボタンの <xref:System.Windows.Forms.ToolBarButton.Style%2A> プロパティをに設定する必要があり <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton> ます。 このプロパティは、クラスのインスタンスを <xref:System.Windows.Forms.ContextMenu> 参照として受け取ります。|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|トグルスタイルのツールバーボタンを部分的にプッシュするかどうかを設定します。 ツールバーボタンの <xref:System.Windows.Forms.ToolBarButton.Style%2A> プロパティをに設定する必要があり <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> ます。|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|トグルスタイルのツールバーボタンが現在プッシュ状態になっているかどうかを設定します。 ツールバーボタンの <xref:System.Windows.Forms.ToolBarButton.Style%2A> プロパティは、またはに設定する必要があり <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton> ます。|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|ツールバーボタンのスタイルを設定します。 列挙体の値のいずれかである必要があり <xref:System.Windows.Forms.ToolBarButtonStyle> ます。|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|ボタンによって表示されるテキスト文字列。|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|ボタンのツールヒントとして表示されるテキスト。|

5. [ **OK** ] をクリックしてダイアログボックスを閉じ、指定したパネルを作成します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolBar>
- [方法: ツール バー ボタンのアイコンを定義する](how-to-define-an-icon-for-a-toolbar-button.md)
- [方法: ツール バー ボタンのメニュー イベントをトリガーする](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar コントロールの概要](toolbar-control-overview-windows-forms.md)
- [ToolBar コントロール](toolbar-control-windows-forms.md)
