---
title: 'チュートリアル : DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: f4fb9c6e7c48a1c6671b14ba05a63dc61195105a
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957618"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a>チュートリアル: 標準型のコレクションのシリアル化

カスタムコントロールによって、コレクションがプロパティとして公開されることがあります。 このチュートリアルでは、クラスを使用して、 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> デザイン時にコレクションをシリアル化する方法を制御する方法について説明します。 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>コレクションプロパティに値を適用すると、プロパティが確実にシリアル化されます。

このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: DesignerSerializationVisibilityAttribute を使用して標準型のコレクションをシリアル化](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))する」を参照してください。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには Visual Studio が必要です。

## <a name="create-a-control-with-a-serializable-collection"></a>シリアル化可能なコレクションを持つコントロールを作成する

最初の手順では、シリアル化可能なコレクションをプロパティとして持つコントロールを作成します。 このコレクションの内容は、[**プロパティ**] ウィンドウからアクセスできる **コレクションエディター** を使用して編集できます。

1. Visual Studio で、Windows コントロールライブラリプロジェクトを作成し、「 **Serializationdemocontrollib**」という名前を指定します。

2. `UserControl1` の名前を `SerializationDemoControl` に変更します。 詳細については、「 [コードシンボルの名前変更のリファクタリング](/visualstudio/ide/reference/rename)」を参照してください。

3. [ **プロパティ** ] ウィンドウで、プロパティの値 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> を **10** に設定します。

4. <xref:System.Windows.Forms.TextBox>にコントロールを配置し `SerializationDemoControl` ます。

5. <xref:System.Windows.Forms.TextBox> コントロールを選択します。 [ **プロパティ** ] ウィンドウで、次のプロパティを設定します。

    |プロパティ|変更後の値|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**Dock**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**スクロールバー**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. **コードエディター** で、にという名前の文字列配列フィールドを宣言 `stringsValue` `SerializationDemoControl` します。

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. `Strings`でプロパティを定義し `SerializationDemoControl` ます。

   > [!NOTE]
   > <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>値は、コレクションのシリアル化を有効にするために使用されます。

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. **F5** キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー** でコントロールを実行します。

9.  <xref:System.Windows.Forms.PropertyGrid> **UserControl テストコンテナー** ので、Strings プロパティを見つけます。 [ **文字列** ] プロパティを選択し、省略記号 ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) を選択して、 ](./media/visual-studio-ellipsis-button.png) **文字列コレクションエディター** を開きます。

10. **文字列コレクションエディター** でいくつかの文字列を入力します。 各文字列の末尾にある **enter** キーを押して区切ります。 文字列の入力が完了したら、[ **OK** ] をクリックします。

   > [!NOTE]
   > 入力した文字列は、のに表示され <xref:System.Windows.Forms.TextBox> `SerializationDemoControl` ます。

## <a name="serialize-a-collection-property"></a>コレクションプロパティをシリアル化する

コントロールのシリアル化動作をテストするには、コントロールをフォームに配置し、コレクション **エディター** を使用してコレクションの内容を変更します。 シリアル化されたコレクションの状態を確認するには、 **Windows フォームデザイナー** がコードを出力する特別なデザイナーファイルを調べます。

1. Windows アプリケーションプロジェクトをソリューションに追加します。 プロジェクトに `SerializationDemoControlTest` という名前を付けます。

2. [ **ツールボックス**] で、[ **Serializationdemocontrollib Components**] という名前のタブを探します。 このタブには、が `SerializationDemoControl` あります。 詳細については、「[チュートリアル : ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)」を参照してください。

3. を `SerializationDemoControl` フォームに配置します。

4. `Strings`[**プロパティ**] ウィンドウでプロパティを見つけます。 `Strings`プロパティをクリックし、[ ![ Visual Studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして、 ](./media/visual-studio-ellipsis-button.png) **文字列コレクションエディター** を開きます。

5. **文字列コレクションエディター** でいくつかの文字列を入力します。 各文字列の末尾で **enter** キーを押して区切ります。 文字列の入力が完了したら、[ **OK** ] をクリックします。

    > [!NOTE]
    > 入力した文字列は、のに表示され <xref:System.Windows.Forms.TextBox> `SerializationDemoControl` ます。

6. **ソリューション エクスプローラー** で、 **[すべてのファイルを表示]** ボタンをクリックします。

7. **Form1** ノードを開きます。 その下には、 **Form1.Designer.cs** または **form1.vb** という名前のファイルがあります。 これは、フォームとその子コントロールのデザイン時の状態を表すコードを **Windows フォームデザイナー** が出力するファイルです。 **コードエディター** でこのファイルを開きます。

8. **Windows フォームデザイナーで生成されたコード** という名前の領域を開き、 **serializationDemoControl1** というラベルが付いたセクションを検索します。 このラベルの下には、コントロールのシリアル化された状態を表すコードがあります。 手順 5. で入力した文字列は、プロパティへの代入の中に表示され `Strings` ます。 C# および Visual Basic の次のコード例では、文字列 "red"、"オレンジ"、および "黄" を入力した場合と同様のコードが表示されます。

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. **コードエディター** で、プロパティのの値 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> をに変更し `Strings` <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden> ます。

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. ソリューションをリビルドし、手順3と4を繰り返します。

> [!NOTE]
> この場合、 **Windows フォームデザイナー** はプロパティに割り当てを出力しません `Strings` 。

## <a name="next-steps"></a>次のステップ

標準型のコレクションをシリアル化する方法を理解したら、カスタムコントロールをデザイン時環境により深く統合することを検討してください。 次のトピックでは、カスタムコントロールのデザイン時統合を強化する方法について説明します。

- [デザイン時アーキテクチャ](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Windows フォーム コントロールの属性](attributes-in-windows-forms-controls.md)

- [デザイナーのシリアル化の概要](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>関連項目

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
