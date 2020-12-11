---
title: 'チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 3fd9175f47f9f1b35743dc69b462227fdfafe55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983444"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成

型から派生した独自のクラスを記述することにより、アプリケーションの <xref:System.Windows.Forms.ToolStrip> コントロールに洗練された外観と動作を与えることができ <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ます。

このチュートリアルでは、コントロールを使用して、 <xref:System.Windows.Forms.ToolStrip> Microsoft® Outlook®によって提供される **ナビゲーションウィンドウ** に似た複合コントロールを作成する方法について説明します。 このチュートリアルでは、次のタスクについて説明します。

- Windows コントロールライブラリプロジェクトを作成しています。

- StackView コントロールのデザイン。

- カスタムレンダラーを実装する。

完了すると、Microsoft Office® XP コントロールの洗練された外観で、再利用可能なカスタムクライアントコントロールを使用できるようになります。

このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: プロフェッショナルスタイルの ToolStrip コントロールを作成](how-to-create-a-professionally-styled-toolstrip-control.md)する」を参照してください。

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、Visual Studio が必要です。

## <a name="create-the-control-library-project"></a>コントロールライブラリプロジェクトを作成する

1. Visual Studio で、という名前の新しい Windows コントロールライブラリプロジェクトを作成 `StackViewLibrary` します。

2. **ソリューションエクスプローラー** で、選択した言語に応じて、"UserControl1.cs" または "UserControl1" という名前のソースファイルを削除して、プロジェクトの既定のコントロールを削除します。

     詳細については、「 [方法: 項目を削除、削除、および除外する](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))」を参照してください。

3. <xref:System.Windows.Forms.UserControl> **Stackviewlibrary** プロジェクトに新しい項目を追加します。 新しいソースファイルにのベース名を指定 `StackView` します。

## <a name="design-the-stackview-control"></a>StackView コントロールのデザイン

コントロールは、 `StackView` 1 つの子コントロールを持つ複合コントロールです <xref:System.Windows.Forms.ToolStrip> 。 複合コントロールの詳細については、「 [カスタムコントロールの種類](varieties-of-custom-controls.md)」を参照してください。

1. **ツールボックス** から <xref:System.Windows.Forms.ToolStrip> デザイン画面にコントロールをドラッグします。

2. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.ToolStrip> 次の表に従ってコントロールのプロパティを設定します。

    |プロパティ|値|
    |--------------|-----------|
    |名前|`stackStrip`|
    |CanOverflow|`false`|
    |ドッキング|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |フォント|`Tahoma, 10pt, style=Bold`|
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |パディング|`0, 7, 0, 0`|
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. Windows フォームデザイナーで、 <xref:System.Windows.Forms.ToolStrip> コントロールの [ **追加** ] ボタンをクリックし、 <xref:System.Windows.Forms.ToolStripButton> コントロールにを追加し `stackStrip` ます。

4. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.ToolStripButton> 次の表に従ってコントロールのプロパティを設定します。

    |プロパティ|値|
    |--------------|-----------|
    |名前|`mailStackButton`|
    |CheckOnClick|true|
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|
    |System.windows.forms.toolstripitem.displaystyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |ImageTransparentColor|`238, 238, 238`|
    |余白|`0, 0, 0, 0`|
    |[間隔]|`3, 3, 3, 3`|
    |Text|**電子**|
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. さらに3つのコントロールについて、手順 7. を繰り返し <xref:System.Windows.Forms.ToolStripButton> ます。

     コントロールに、、およびという名前を指定し `calendarStackButton` `contactsStackButton` `tasksStackButton` ます。 プロパティの値 <xref:System.Windows.Forms.Control.Text%2A> をそれぞれ **Calendar**、 **Contacts**、および **Tasks** に設定します。

## <a name="handle-events"></a>イベントを処理する

コントロールを正しく動作させるには、2つのイベントが重要です `StackView` 。 イベントを処理して <xref:System.Windows.Forms.UserControl.Load> 、コントロールを正しく配置します。 それぞれのイベントを処理して、コントロール <xref:System.Windows.Forms.ToolStripItem.Click> <xref:System.Windows.Forms.ToolStripButton> `StackView` の状態の動作をコントロールと同様にし <xref:System.Windows.Forms.RadioButton> ます。

1. [Windows フォームデザイナーで、コントロールを選択し `StackView` ます。

2. **[プロパティ]** ウィンドウで、**[イベント]** をクリックします。

3. イベントハンドラーを生成するには、Load イベントをダブルクリックし `StackView_Load` ます。

4. `StackView_Load` イベント ハンドラーで、次のコードをコピーして貼り付けます。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. [Windows フォームデザイナーで、コントロールを選択し `mailStackButton` ます。

6. **[プロパティ]** ウィンドウで、**[イベント]** をクリックします。

7. Click イベントをダブルクリックします。

     Windows フォームデザイナーによって、イベントハンドラーが生成され `mailStackButton_Click` ます。

8. `mailStackButton_Click`イベントハンドラーの名前をに変更 `stackButton_Click` します。

     詳細については、「 [コードシンボルの名前変更のリファクタリング](/visualstudio/ide/reference/rename)」を参照してください。

9. イベントハンドラーに次のコードを挿入し `stackButton_Click` ます。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. [Windows フォームデザイナーで、コントロールを選択し `calendarStackButton` ます。

11. [ **プロパティ** ] ウィンドウで、click イベントをイベントハンドラーに設定し `stackButton_Click` ます。

12. コントロールとコントロールに対して、手順 10. および 11. を繰り返し `contactsStackButton` `tasksStackButton` ます。

## <a name="define-icons"></a>アイコンの定義

各 `StackView` ボタンにはアイコンが関連付けられています。 便宜上、各アイコンは Base64 でエンコードされた文字列として表され、が作成される前に逆シリアル化され <xref:System.Drawing.Bitmap> ます。 運用環境では、ビットマップデータをリソースとして格納し、アイコンが Windows フォームデザイナーに表示されます。 詳細については、「 [方法: Windows フォームに背景画像を追加](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))する」を参照してください。

1. コードエディターで、次のコードをクラス定義に挿入し `StackView` ます。 このコードでは、アイコンのビットマップを初期化し <xref:System.Windows.Forms.ToolStripButton> ます。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. `InitializeImages`クラスコンストラクターにメソッドの呼び出しを追加 `StackView` します。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a>カスタムレンダラーを実装する

`StackView`クラスから派生するクラスを実装するコントロールのほとんどの要素をカスタマイズでき <xref:System.Windows.Forms.ToolStripRenderer> ます。 この手順では、 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> グリップをカスタマイズし、コントロールのグラデーションの背景を描画するクラスを実装し <xref:System.Windows.Forms.ToolStripButton> ます。

1. コントロール定義に次のコードを挿入し `StackView` ます。

     これは、クラスの定義です。これは、、、およびの各メソッドをオーバーライドして `StackRenderer` <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip> 、 <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> カスタムの外観を生成します。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. `StackView`コントロールのコンストラクターで、クラスの新しいインスタンスを作成 `StackRenderer` し、このインスタンスを `stackStrip` コントロールのプロパティに割り当て <xref:System.Windows.Forms.ToolStrip.Renderer%2A> ます。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a>StackView コントロールをテストする

`StackView`コントロールはクラスから派生 <xref:System.Windows.Forms.UserControl> します。 そのため、 **UserControl テストコンテナー** を使用してコントロールをテストできます。 詳細については、「 [方法: UserControl の Run-Time 動作をテストする](how-to-test-the-run-time-behavior-of-a-usercontrol.md)」を参照してください。

1. **F5** キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー** を開始します。

2. コントロールのボタンの上にポインターを移動し、 `StackView` ボタンをクリックすると、選択した状態の外観が表示されます。

## <a name="next-steps"></a>次のステップ

このチュートリアルでは、Office XP コントロールのプロフェッショナルな外観を使用して、再利用可能なカスタムクライアントコントロールを作成しました。 コントロールファミリは、 <xref:System.Windows.Forms.ToolStrip> 他のさまざまな用途に使用できます。

- を使用して、コントロールのショートカットメニューを作成 <xref:System.Windows.Forms.ContextMenuStrip> します。 詳細については、「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。

- 自動的に設定された標準メニューを使用してフォームを作成します。 詳細については、「 [チュートリアル: フォームに標準メニュー項目を提供する](walkthrough-providing-standard-menu-items-to-a-form.md)」を参照してください。

- ドッキングコントロールを使用して、マルチドキュメントインターフェイス (MDI) フォームを作成 <xref:System.Windows.Forms.ToolStrip> します。 詳細については、「 [方法: メニューのマージと ToolStrip コントロールを使用して MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)する」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip コントロール](toolstrip-control-windows-forms.md)
- [方法: フォームに標準メニュー項目を追加する](how-to-provide-standard-menu-items-to-a-form.md)
