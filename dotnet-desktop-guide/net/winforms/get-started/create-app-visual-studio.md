---
title: Visual Studio での新しいアプリの作成に関するチュートリアル
description: このチュートリアルでは、Visual Studio 2019 を使用して .NET 用の新しい Windows フォーム アプリを作成する方法について説明します。
ms.date: 10/26/2020
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: db0712aa642e54373f686fdd24a4747bf2d195e3
ms.sourcegitcommit: e8e3f6f23b5ddf9f5c4fe1ec5f6e0a8a609d49c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "97004733"
---
# <a name="tutorial-create-a-new-winforms-app-windows-forms-net"></a>チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)

この短いチュートリアルでは、Visual Studio で新しい Windows フォーム (WinForms) アプリを作成する方法について説明します。 最初のアプリが生成された後、コントロールを追加する方法と、イベントを処理する方法について説明します。 このチュートリアルを終了すると、リスト ボックスに名前を追加する簡単なアプリが作成されます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

このチュートリアルでは、以下の内容を学習します。

> [!div class="checklist"]
>
> - 新しい WinForms アプリを作成する
> - フォームにコントロールを追加する
> - コントロール イベントを処理してアプリの機能を提供する
> - アプリを実行する

## <a name="prerequisites"></a>前提条件

- [Visual Studio 2019 バージョン 16.8 以降のバージョン](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)
  - [Visual Studio デスクトップ ワークロード](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)を選択します
  - [.NET 5 の個別のコンポーネント](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)を選択します

## <a name="create-a-winforms-app"></a>WinForms アプリを作成する

新しいアプリを作成するための最初のステップは、Visual Studio を開き、テンプレートからアプリを生成することです。

01. Visual Studio を開きます。
01. **[新しいプロジェクトの作成]** を選択します。

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Visual Studio 2019 for .NET で新しい Windows フォーム プロジェクトを作成する":::

01. **[テンプレートの検索]** ボックスに「**winforms**」と入力し、<kbd>Enter</kbd> キーを押します。
01. **[コード言語]** ドロップダウンで、 **[C#]** または **[Visual Basic]** を選択します。
01. テンプレートの一覧で **Windows フォーム アプリ (.NET)** を選択し、 **[次へ]** をクリックします。

    > [!IMPORTANT]
    > **Windows フォーム アプリ (.NET _Framework_)** テンプレートは選択しないでください。

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="Visual Studio 2019 for .NET で Windows フォーム テンプレートを検索する":::

01. **[新しいプロジェクトの構成]** ウィンドウで、 **[プロジェクト名]** を「**Names**」に設定し、 **[作成]** をクリックします。

    **[場所]** の設定を調整することで、プロジェクトを別のフォルダーに保存することもできます。

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="Visual Studio 2019 for .NET で新しい Windows フォーム プロジェクトを構成する":::

アプリが生成されると、Visual Studio のデザイナー ペインに既定のフォーム _Form1_ が開かれます。 フォーム デザイナーが表示されない場合は、 **[ソリューション エクスプローラー]** ペインでフォームをダブルクリックして、デザイナー ウィンドウを開きます。

### <a name="important-parts-of-visual-studio"></a>Visual Studio の重要な部分

Visual Studio での WinForms のサポートには、アプリを作成するときに対話する 4 つの重要なコンポーネントがあります。

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text=".NET 用の Windows フォーム プロジェクトを作成するときに理解しておく必要のある Visual Studio の重要なコンポーネント":::

01. ソリューション エクスプローラー

    プロジェクトのファイル、コード、フォーム、リソースのすべてがこのペインに表示されます。

02. Properties

    このペインには、選択した項目に基づいて構成できるプロパティ設定が表示されます。 たとえば、 **[ソリューション エクスプローラー]** から項目を選択した場合、そのファイルに関連するプロパティ設定が表示されます。 **[デザイナー]** でオブジェクトを選択した場合は、コントロールまたはフォームの設定が表示されます。

03. フォーム デザイナー

    これは、フォーム用のデザイナーです。 対話型であり、 **[ツールボックス]** からオブジェクトをドラッグ アンド ドロップすることができます。 デザイナーで項目を選択して移動することにより、アプリのユーザー インターフェイス (UI) を視覚的に作成できます。

04. ツールボックス

    ツールボックスには、フォームに追加できるすべてのコントロールが含まれています。 現在のフォームにコントロールを追加するには、コントロールをダブルクリックするか、コントロールをドラッグ アンド ドロップします。

## <a name="add-controls-to-the-form"></a>コントロールをフォームに追加する

_Form1_ のフォーム デザイナーを開いた状態で、 **[ツールボックス]** ペインを使用して、次のコントロールをフォームに追加します。

- ラベル
- Button
- Listbox
- テキストボックス

次の設定に従って、コントロールの位置とサイズを設定できます。 次に示すスクリーンショットと一致するように視覚的に動かすか、各コントロールをクリックして **[プロパティ]** ペインで設定を構成します。 フォームのタイトル領域をクリックして、フォームを選択することもできます。

| Object      | 設定  | 値      |
|-------------|----------|------------|
| **形式**    | Text     | `Names`    |
|             | サイズ     | `268, 180` |
|             |          |            |
| **Label**   | 場所 | `12, 9`    |
|             | Text     | `Names`    |
|             |          |            |
| **Listbox** | 名前     | `lstNames` |
|             | 場所 | `12, 27`   |
|             | サイズ     | `120, 94`  |
|             |          |            |
| **テキスト ボックス** | 名前     | `txtName`  |
|             | 場所 | `138, 26`  |
|             | サイズ     | `100, 23`  |
|             |          |            |
| **Button**  | 名前     | `btnAdd`   |
|             | 場所 | `138, 55`  |
|             | サイズ     | `100, 23`  |
|             | Text     | `Add Name` |

次のようなフォームがデザイナーに表示されます。

:::image type="content" source="media/create-app-visual-studio/vs-form-preview.png" alt-text="Windows フォーム for .NET 用のフォームが開かれた Visual Studio 2019 デザイナー":::

## <a name="handle-events"></a>イベントを処理する

フォームへのすべてのコントロールのレイアウトが済んだので、コントロールのイベントを処理してユーザー入力に応答する必要があります。 フォーム デザイナーをまだ開いたままにして、次の手順を実行します。

01. フォーム上のボタン コントロールを選択します。
01. **[プロパティ]** ペインでイベント アイコン :::image type="icon" source="media/create-app-visual-studio/icon-events.png" border="false"::: をクリックして、ボタンのイベントの一覧を表示します。
01. **Click** イベントを見つけてダブルクリックし、イベント ハンドラーを生成します。

    この操作により、次のコードがフォームに追加されます。

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {

    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

    End Sub
    ```

    このハンドラーに作成するコードにより、`txtName` テキスト ボックス コントロールで指定された名前を、`lstNames` リスト ボックス コントロールに追加します。 ただし、名前の追加に 2 つの条件を設けます。指定された名前が空白であってはならず、名前が既に存在していてはなりません。

01. 次のコードでは、名前を `lstNames` コントロールに追加する方法を示します。

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {
        if (!string.IsNullOrWhiteSpace(txtName.Text) && !lstNames.Items.Contains(txtName.Text))
            lstNames.Items.Add(txtName.Text);
    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click
        If Not String.IsNullOrWhiteSpace(txtName.Text) And Not lstNames.Items.Contains(txtName.Text) Then
            lstNames.Items.Add(txtName.Text)
        End If
    End Sub
    ```

## <a name="run-the-app"></a>アプリを実行する

イベントをコーディングしたので、<kbd>F5</kbd> キーを押すか、メニューから **[デバッグ]**  >  **[デバッグの開始]** を選択して、アプリを実行できます。 フォームが表示され、テキスト ボックスに名前を入力し、ボタンをクリックすることによってそれを追加できます。

:::image type="content" source="media/create-app-visual-studio/app-running.png" alt-text="Windows フォーム for .NET アプリの実行。":::

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [Windows フォームの詳細を学習する](../overview/index.md)
