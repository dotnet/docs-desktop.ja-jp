---
title: 'チュートリアル: 標準メニュー項目をフォームに用意する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982708"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>チュートリアル: 標準メニュー項目をフォームに用意する

フォームの標準のメニューを <xref:System.Windows.Forms.MenuStrip> コントロールに提供できます。

このチュートリアルでは、コントロールを使用して標準メニューを作成する方法について説明 <xref:System.Windows.Forms.MenuStrip> します。 フォームは、ユーザーがメニュー項目を選択したときにも応答します。 このチュートリアルでは、次のタスクについて説明します。

- Windows フォームプロジェクトを作成しています。

- 標準メニューを作成する。

- コントロールを作成する <xref:System.Windows.Forms.StatusStrip> 。

- メニュー項目の選択を処理しています。

完了すると、コントロールにメニュー項目の選択項目を表示する標準メニューを持つフォームが作成され <xref:System.Windows.Forms.StatusStrip> ます。

このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: フォームに標準メニュー項目を提供](how-to-provide-standard-menu-items-to-a-form.md)する」を参照してください。

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、Visual Studio が必要です。

## <a name="create-the-project"></a>プロジェクトを作成する

1. Visual Studio で、 **standardmenuform** という名前の Windows アプリケーションプロジェクトを作成します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。

2. [Windows フォームデザイナーで、フォームを選択します。

## <a name="create-a-standard-menu"></a>標準メニューを作成する

Windows フォームデザイナーでは、標準の <xref:System.Windows.Forms.MenuStrip> メニュー項目を使用してコントロールを自動的に設定できます。

1. [ **ツールボックス**] から <xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。

2. <xref:System.Windows.Forms.MenuStrip>コントロールの [デザイナーアクション] グリフ ( ![ 小さい黒い矢印 ](./media/designer-actions-glyph.gif) ) をクリックし、[**標準項目の挿入**] を選択します。

     <xref:System.Windows.Forms.MenuStrip>コントロールには、標準のメニュー項目が設定されます。

3. 既定のメニュー項目と対応するアイコンを表示するには、[ **ファイル** ] メニュー項目をクリックします。

## <a name="create-a-statusstrip-control"></a>StatusStrip コントロールを作成する

コントロールを使用し <xref:System.Windows.Forms.StatusStrip> て、Windows フォームアプリケーションの状態を表示します。 現在の例では、ユーザーが選択したメニュー項目がコントロールに表示され <xref:System.Windows.Forms.StatusStrip> ます。

1. [ **ツールボックス**] から <xref:System.Windows.Forms.StatusStrip> コントロールをフォームにドラッグします。

     コントロールは、 <xref:System.Windows.Forms.StatusStrip> フォームの下部に自動的にドッキングされます。

2. コントロール <xref:System.Windows.Forms.StatusStrip> のドロップダウンボタンをクリックし、[ **statuslabel** ] を選択してコントロールをコントロールに追加し <xref:System.Windows.Forms.ToolStripStatusLabel> <xref:System.Windows.Forms.StatusStrip> ます。

## <a name="handle-item-selection"></a>項目の選択の処理

<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>ユーザーがメニュー項目を選択したときに応答するイベントを処理します。

1. 「標準メニューの作成」セクションで作成した [ **ファイル** ] メニュー項目をクリックします。

2. **[プロパティ]** ウィンドウで、**[イベント]** をクリックします。

3. <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> イベントをダブルクリックします。

     Windows フォームデザイナーは、イベントのイベントハンドラーを生成し <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> ます。

4. イベントハンドラーに次のコードを挿入します。

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. `UpdateStatus`ユーティリティメソッドの定義をフォームに挿入します。

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>チェックポイント-フォームのテスト

1. **F5** キーを押して、フォームをコンパイルして実行します。

2. [ **ファイル** ] メニュー項目をクリックして、メニューを開きます。

3. [ **ファイル** ] メニューのいずれかの項目をクリックして選択します。

     コントロールには、 <xref:System.Windows.Forms.StatusStrip> 選択した項目が表示されます。

## <a name="next-steps"></a>次のステップ

このチュートリアルでは、標準メニューを使用してフォームを作成しました。 コントロールファミリは、 <xref:System.Windows.Forms.ToolStrip> 他のさまざまな用途に使用できます。

- を使用して、コントロールのショートカットメニューを作成 <xref:System.Windows.Forms.ContextMenuStrip> します。 詳細については、「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。

- ドッキングコントロールを使用して、マルチドキュメントインターフェイス (MDI) フォームを作成 <xref:System.Windows.Forms.ToolStrip> します。 詳細については、「 [チュートリアル: メニューのマージと ToolStrip コントロールを使用した MDI フォームの作成](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)」を参照してください。

- コントロールに <xref:System.Windows.Forms.ToolStrip> プロフェッショナルな外観を与えます。 詳細については、「 [方法: アプリケーションの ToolStrip レンダラーを設定する](how-to-set-the-toolstrip-renderer-for-an-application.md)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip コントロール](menustrip-control-windows-forms.md)
