---
title: Visual Studio での新しいアプリの作成に関するチュートリアル
description: このチュートリアルに従って、Visual Studio 2019 を使用して .NET 用の新しい WPF アプリを作成する方法について学習します。
ms.date: 01/18/2021
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: b2769d4901b211cf5bc7cffbe4c1bf65d26a0758
ms.sourcegitcommit: 455923e44f1e8df30a233807a54ded94ddc1cf62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99510065"
---
# <a name="tutorial-create-a-new-wpf-app-wpf-net"></a>チュートリアル: 新しい WPF アプリを作成する (WPF .NET)

この短いチュートリアルでは、Visual Studio で新しい Windows Presentation Foundation (WPF) アプリを作成する方法について学習します。 最初のアプリが生成された後、コントロールを追加する方法と、イベントを処理する方法について説明します。 このチュートリアルを終了すると、リスト ボックスに名前を追加する簡単なアプリが作成されます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

このチュートリアルでは、以下の内容を学習します。

> [!div class="checklist"]
>
> - 新しい WPF アプリを作成する
> - フォームにコントロールを追加する
> - コントロール イベントを処理してアプリの機能を提供する
> - アプリを実行する

このチュートリアルに従ってビルドするアプリのプレビューを以下に示します。

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="チュートリアルで完成した WPF 用のサンプル アプリ":::

## <a name="prerequisites"></a>前提条件

- [Visual Studio 2019 バージョン 16.8.4 以降のバージョン](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)
  - [Visual Studio デスクトップ ワークロード](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)を選択します
  - [.NET 5 の個別のコンポーネント](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)を選択します

## <a name="create-a-wpf-app"></a>WPF アプリを作成する

新しいアプリを作成するための最初のステップは、Visual Studio を開き、テンプレートからアプリを生成することです。

01. Visual Studio を開きます。
01. **[新しいプロジェクトの作成]** を選択します。

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Visual Studio 2019 for .NET で新しい WPF プロジェクトを作成する":::

01. **[テンプレートの検索]** ボックスに「**wpf**」と入力してから、<kbd>Enter</kbd> キーを押します。
01. **[コード言語]** ドロップダウンで、 **[C#]** または **[Visual Basic]** を選択します。
01. テンプレートの一覧で、 **[WPF アプリケーション]** を選んでから、 **[次へ]** を選択します。

    > [!IMPORTANT]
    > **[WPF Application (.NET _Framework_)]\(WPF アプリケーション (.NET Framework)\)** テンプレートは選択しないでください。

    :::image type="content" source="media/create-app-visual-studio/vs-template-search-16.8.png" alt-text="Visual Studio 2019 for .NET で WPF テンプレートを検索する":::

01. **[新しいプロジェクトの構成]** ウィンドウで、次の操作を行います。

    01. **[プロジェクト名]** ボックスに、「**Names**」と入力します。
    01. **[ソリューションとプロジェクトを同じディレクトリに配置する]** チェック ボックスをオンにします。
    01. 必要に応じて、別の **[場所]** を選んでコードを保存します。
    01. **[作成]** ボタンを選択します。

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-16.8.png" alt-text="Visual Studio 2019 for .NET で新しい WPF プロジェクトを構成する":::

<!-- THIS IS FOR 16.9 when it's released. Also, change the last child step of the previous step to **Next**

01. In the **Additional information** window, select **.NET 5.0 (Current)** for **Target Framework** and make sure that the **Run on .NET Framework** check box is cleared. Select the **Create** button.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-next.png" alt-text="Select target framework for new WPF project in Visual Studio 2019 for .NET":::
-->

アプリが生成されると、Visual Studio で既定のウィンドウ _MainWindow_ の XAML デザイナー ペインが開くはずです。 デザイナーが表示されない場合は、 **[ソリューション エクスプローラー]** ペインで _MainWindow.xaml_ ファイルをダブルクリックしてデザイナーを開きます。

### <a name="important-parts-of-visual-studio"></a>Visual Studio の重要な部分

Visual Studio での WPF のサポートには、アプリを作成するときにやりとりする 5 つの重要なコンポーネントがあります。

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text=".NET 用の WPF プロジェクトを作成するときに理解しておく必要のある Visual Studio の重要なコンポーネント":::

01. ソリューション エクスプローラー

    プロジェクトのファイル、コード、ウィンドウ、リソースのすべてがこのペインに表示されます。

02. Properties

    このペインには、選択した項目に基づいて構成できるプロパティ設定が表示されます。 たとえば、 **[ソリューション エクスプローラー]** から項目を選択した場合、そのファイルに関連するプロパティ設定が表示されます。 **[デザイナー]** でオブジェクトを選択した場合は、その項目の設定が表示されます。

03. ツールボックス

    ツールボックスには、フォームに追加できるすべてのコントロールが含まれています。 現在のフォームにコントロールを追加するには、コントロールをダブルクリックするか、コントロールをドラッグ アンド ドロップします。

04. XAML デザイナー

    これは、XAML ドキュメント用のデザイナーです。 対話型であり、 **[ツールボックス]** からオブジェクトをドラッグ アンド ドロップすることができます。 デザイナーで項目を選択して移動することにより、アプリのユーザー インターフェイス (UI) を視覚的に作成できます。

    デザイナーとエディターの両方が表示されている場合は、一方に対する変更がもう一方に反映されます。 デザイナーで項目を選択すると、 **[プロパティ]** ペインに、そのオブジェクトに関するプロパティと属性が表示されます。

05. XAML コード エディター

    これは、XAML ドキュメント用の XAML コード エディターです。 XAML コード エディターは、デザイナーを使用せずに手動で UI を作成する手段です。 デザイナーにコントロールが追加されたときに、そのデザイナーによってコントロールのプロパティの値が推論される場合があります。 XAML コード エディターを使用すると、より多くの制御を行うことができます。

    デザイナーとエディターの両方が表示されている場合は、一方に対する変更がもう一方に反映されます。 コード エディターでテキスト キャレットを移動すると、 **[プロパティ]** ペインに、そのオブジェクトに関するプロパティと属性が表示されます。

## <a name="target-net-50"></a>ターゲット .NET 5.0

プロジェクトを作成した後、ターゲット フレームワークを .NET 5.0 に変更します。 **[ソリューション エクスプローラー]** で、_Names_ プロジェクト ファイルをダブルクリックします。 これにより、プロジェクト ファイルが開き、編集できます。 `<TargetFramework>` 要素を `net5.0-windows` に設定します。

```xml
<TargetFramework>net5.0-windows</TargetFramework>
```

プロジェクト ファイルを保存してから、エディター タブを閉じます。

## <a name="examine-the-xaml"></a>XAML を確認する

プロジェクトが作成された後、XAML コード エディターが表示されます。ここには、ウィンドウを表示するための最小限の XAML コードがあります。 エディターが開いていない場合は、 **[ソリューション エクスプローラー]** で _MainWindow.xaml_ 項目をダブルクリックします。 次のような XAML が表示されるはずです。

```xaml
<Window x:Class="Names.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Names"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>

    </Grid>
</Window>
```

わかりやすくするために、この XAML コードを分割してみましょう。 XAML は、WPF で使用されるコンパイラによって処理できるシンプルな XML です。 WPF UI を記述し、.NET コードとやりとりします。 XAML を理解するには、少なくとも XML の基本をよく理解しておく必要があります。

ドキュメントのルート `<Window>` は、XAML ファイルによって記述されるオブジェクトの型を表します。 次の 8 つの属性が宣言されており、これらは一般的に 3 つのカテゴリに属しています。

- 名前空間

  XML 名前空間で XML に構造体が提供され、これにより、ファイル内での宣言が許可されるものとされないものが決まります。

  メインの `xmlns` 属性で、ファイル全体の XML 名前空間がインポートされます。この場合、WPF によって宣言される型にマップされます。 その他の XML 名前空間でプレフィックスが宣言され、XAML ファイル用のその他の型とオブジェクトがインポートされます。 たとえば、`xmlns:local` 名前空間の場合、`local` プレフィックスが宣言され、プロジェクトによって宣言されたオブジェクト (`Names` コード名前空間で宣言されたもの) にマップされます。

- `x:Class` 属性

  この属性で、`<Window>` がコードによって定義された型にマップされます。これは、`Names.MainWindow` クラスである _MainWindow.xaml.cs_ または _MainWindow.xaml.vb_ ファイルです。

- `Title` 属性

  XAML オブジェクトで宣言される通常の属性により、そのオブジェクトのプロパティが設定されます。 この場合、`Title` 属性によって `Window.Title` プロパティが設定されます。

## <a name="change-the-window"></a>ウィンドウを変更する

まず、プロジェクトを実行して、既定の出力を確認してみましょう。 ポップアップ表示されるウィンドウには、コントロールはなく、**MainWindow** というタイトルが示されます。

:::image type="content" source="media/create-app-visual-studio/app-default.png" alt-text="空の WPF アプリ":::

例のアプリの場合、このウィンドウは大きすぎて、タイトル バーがわかりにくくなっています。 XAML の適切な属性を次の値に変更して、ウィンドウのタイトルとサイズを変更します。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/Start.xaml" highlight="8":::

## <a name="prepare-the-layout"></a>レイアウトを準備する

WPF には、さまざまなレイアウト コントロールを持つ強力なレイアウト システムが用意されています。 レイアウト コントロールは、子コントロールを配置したりサイズを設定したりするのに役立ち、自動的に実行することもできます。 この XAML に用意されている既定のレイアウト コントロールは、`<Grid>` コントロールです。

`Grid` コントロールを使用すると、テーブルと同じように行と列を定義し、特定の行と列の組み合わせの境界内にコントロールを配置できます。 `Grid` には、任意の数の子コントロールまたはその他のレイアウト コントロールを追加できます。 たとえば、特定の行と列の組み合わせに別の `Grid` コントロールを配置できます。その後、新しい `Grid` でより多くの行と列を定義し、独自の子を持つことができます。

`<Grid>` コントロールにより、コントロールが配置される行と列が定義されます。 グリッドには常に単一の行と列が宣言されています。つまり、グリッドは既定で単一のセルになります。 その場合、実際にはそれほど柔軟にコントロールを配置できません。

新しい行と列を追加する前に、`<Grid>` 要素に新しい属性 (`Margin="10"`) を追加します。 これでウィンドウからグリッドがインセットされ、少し見栄えが良くなります。

次に、2 つの行と 2 つの列を定義し、グリッドを 4 つのセルに分割します。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep2.xaml" highlight="9-21":::

XAML コード エディターまたは XAML デザイナーでグリッドを選択すると、XAML デザイナーに各行と列が表示されることがわかります。

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns.png" alt-text="グリッドに余白が設定されている WPF アプリ":::

## <a name="add-the-first-control"></a>最初のコントロールを追加する

これでグリッドが作成されたので、コントロールの追加を開始できます。 まず、ラベル コントロールから始めます。 `<Grid>` 要素内で、行と列の定義の後に新しい `<Label>` 要素を作成し、`Names` の文字列値を指定します。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep3.xaml" range="9-23" highlight="13":::

`<Label>Names</Label>` でコンテンツ `Names` が定義されます。 コントロールによっては、コンテンツの処理方法が理解されるものとされないものがあります。 コントロールのコンテンツは、`Content` プロパティにマップされます。 コンテンツを XAML 属性構文で設定する場合は、この `<Label Content="Names" />` 形式を使用します。 どちらの方法でも、テキスト `Names` を表示するようにラベルのコンテンツを設定することで同じことが行われます。

しかし、問題があります。グリッドの最初の行と列に自動的に割り当てられたラベルが、ウィンドウの半分を占めています。 最初の行では、その行をラベルに使用するだけなので、それほど多くのスペースは必要ありません。 最初の `<RowDefinition>` の `Height` 属性を `*` から `Auto` に変更します。 `Auto` 値を指定すると、グリッド行のサイズがそのコンテンツ (この場合はラベル コントロール) のサイズに自動的に設定されます。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep4.xaml" range="11-14" highlight="2":::

デザイナーに、使用可能な高さを占める量が少なくなったラベルが表示されるようになったことに注目してださい。 これで、次の行の占有スペースが増えました。 ほとんどのコントロールで、見栄えを最高のものにするために占有する必要がある何らかの高さと幅の値が定義されます。 ラベル コントロールの場合、高さの値があるため、確実に読み取ることができます。

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns-label.png" alt-text="グリッドに余白が設定され、最初の行にラベル コントロールがある WPF アプリ":::

### <a name="control-placement"></a>コントロールの配置

それでは、コントロールの配置について説明します。 上のセクションで作成されたラベルは、グリッドの行 0 と列 0 に自動的に配置されました。 行と列の番号付けは 0 から始まり、新しい行または列ごとに 1 ずつ増加します。 コントロールにグリッドに関する知識はないため、コントロールでグリッド内の配置を制御するプロパティは定義されません。 コントロールは、コントロールを配置する方法を定義する独自の規則セットを持つ他のレイアウト コントロール内に配置されている場合もあります。

コントロールにグリッドに関する知識がない場合に、別の行または列を使用するようにコントロールに指示するにはどうすればよいでしょうか? 添付プロパティがあります。 グリッドでは、WPF によって提供される強力なプロパティ システムを利用します。 そのグリッドにより、子コントロールで宣言および使用できる新しいプロパティが定義されます。 これらのプロパティは実際にはコントロール自体には存在せず、コントロールがグリッドに追加されたときにそのグリッドによって添付されます。

グリッドにより、子コントロールの行と列の配置を決定する 2 つのプロパティ (`Grid.Row` と `Grid.Column`) が定義されます。 これらのプロパティがコントロールから省略されている場合、既定値の 0 が設定されていることが示されるため、コントロールはグリッドの行 `0` と列 `0` に配置されます。 `Grid.Column` 属性を `1` に設定し、`<Label>` コントロールの配置を変更してみてください。

```xaml
<Label Grid.Column="1">Names</Label>
```

これでラベルが 2 番目の列にどのように移動されたかに注目してください。 `Grid.Row` および `Grid.Column` 添付プロパティを使用して、次に作成するコントロールを配置できます。 しかしここでは、ラベルを行 0 に復元します。

## <a name="create-the-name-list-box"></a>名前リスト ボックスを作成する

これでグリッドのサイズが正しく設定され、ラベルが作成されたので、そのラベルの下の行にリスト ボックス コントロールを追加します。 リスト ボックスは、行 `1` と列 `0` に配置されます。 また、このコントロールに `lstNames` という名前を付けます。 コントロールに名前を付けたら、分離コードで参照できます。 名前は、`x:Name` 属性を使用してコントロールに割り当てられます。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls1.xaml" range="9-24" highlight="14":::

## <a name="add-the-remaining-controls"></a>残りのコントロールを追加する

追加する最後の 2 つのコントロールは、テキスト ボックスとボタンです。ユーザーはこれらを使用して、リスト ボックスに追加する名前を入力します。 しかし、グリッド用にさらに多くの行と列を作成してみるのではなく、これらのコントロールを `<StackPanel>` レイアウト コントロールに配置します。

スタック パネルとグリッドでは、コントロールの配置方法が異なります。 グリッドには `Grid.Row` および `Grid.Column` 添付プロパティを使用してコントロールを配置する場所を指示しますが、スタック パネルは、最初のコントロールを配置し、その後に次のコントロールを配置して、すべてのコントロールが配置されるまで続行することで自動的に動作します。 各コントロールは他のものの下に "スタック" されます。

リスト ボックスの後に `<StackPanel>` コントロールを作成し、グリッド行 `1` 列 `1` に配置します。 値が `5,0,0,0` の `Margin` という名前の別の属性を追加します。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel1":::

その `Margin` 属性はグリッドで以前に使用されたものですが、入力したのは単一の値 `10` のみです。 ここでは、スタック パネルで `5,0,0,0` という値を使用しました。 余白は `Thickness` 型で、両方の値を解釈できます。 太さでは、四角形のフレームの各辺の **左**、**上**、**右**、**下** の周囲のスペースがそれぞれ定義されます。 余白の値が単一の値の場合は、4 辺すべてにその値が使用されます。

次に、`<StackPanel>` に `<TextBox>` および `<Button>` コントロールを作成します。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel2":::

ウィンドウのレイアウトが完了しました。 しかし、アプリには実際に機能するロジックがありません。 次は、コントロール イベントをコードにフックし、アプリに実際に何かを実行させる必要があります。

## <a name="add-code-for-the-click-event"></a>Click イベントのコードを追加する

作成した `<Button>` には、ユーザーがボタンを押したときに発生する `Click` イベントがあります。 このイベントをサブスクライブし、リスト ボックスに名前を追加するコードを追加することができます。 XAML 属性を追加することによってコントロールのプロパティを設定するのと同じように、XAML 属性を使用してイベントをサブスクライブできます。 `Click` 属性を `ButtonAddName_Click` に設定します

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml" id="ButtonEvent" highlight="3":::

ここで、ハンドラー コードを生成する必要があります。 `ButtonAddName_Click` を右クリックし、 **[定義へ移動]** を選択します。 これにより、入力したハンドラー名と一致するメソッドが分離コードで自動的に生成されます。

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml.cs" id="ButtonEvent":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/MoreControls3.xaml.vb" id="ButtonEvent":::

次は、これらの 3 つの手順を行うために以下のコードを追加します。

01. テキスト ボックスに名前が含まれていることを確認します。
01. テキスト ボックスに入力された名前がまだ存在しないことを確認します。
01. リスト ボックスに名前を追加します。

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/Final.xaml.cs" id="FinalCode":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/Final.xaml.vb" id="FinalCode":::

## <a name="run-the-app"></a>アプリを実行する

イベントをコーディングしたので、<kbd>F5</kbd> キーを押すか、メニューから **[デバッグ]**  >  **[デバッグの開始]** を選択して、アプリを実行できます。 ウィンドウが表示され、テキスト ボックスに名前を入力し、ボタンをクリックすることでそれを追加できます。

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text=".NET アプリ用の Windows Presentation Foundation (WPF) の実行。":::

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [Windows Presentation Foundation についてさらに学習する](../overview/index.md)
