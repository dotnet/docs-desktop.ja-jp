---
title: 既存のコントロールから継承する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 7d9766c1bb1812cc5978221ccec42f5eb2c8c4ff
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957722"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>方法 : 既存の Windows フォーム コントロールから継承する

既存のコントロールの機能を拡張する場合は、継承によって既存のコントロールから派生したコントロールを作成できます。 既存のコントロールから継承すると、そのコントロールのすべての機能およびビジュアル プロパティが引き継がれます。 たとえば、から継承されたコントロールを作成した場合、 <xref:System.Windows.Forms.Button> 新しいコントロールは標準コントロールとまったく同じように見え、動作し <xref:System.Windows.Forms.Button> ます。 その後で、カスタム メソッドやカスタム プロパティの実装によって、新しいコントロールの機能を拡張または変更できます。 一部のコントロールでは、メソッドをオーバーライドすることによって、継承されたコントロールの外観を変更することもでき <xref:System.Windows.Forms.Control.OnPaint%2A> ます。

## <a name="to-create-an-inherited-control"></a>継承したコントロールを作成するには

1. Visual Studio で、新しい **Windows フォームアプリケーション** プロジェクトを作成します。

1. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。

    **[新しい項目の追加]** ダイアログ ボックスが表示されます。

1. **[新しい項目の追加]** ダイアログ ボックスの **[カスタム コントロール]** をダブルクリックします。

    新しいカスタム コントロールがプロジェクトに追加されます。

1. を使用している場合:

    - Visual Basic、 **ソリューションエクスプローラー** の上部にある [ **すべてのファイルを表示**] をクリックします。 CustomControl1.vb を展開し、コード エディターで CustomControl1.Designer.vb を開きます。
    - C# では、コードエディターで CustomControl1.cs を開きます。

1. から継承するクラス宣言を探し <xref:System.Windows.Forms.Control> ます。

1. 基底クラスを継承元のコントロールに変更します。

     たとえば、から継承する場合は、 <xref:System.Windows.Forms.Button> クラスの宣言を次のように変更します。

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Visual Basic を使用している場合は、CustomControl1.Designer.vb を保存して閉じます。 コード エディターで CustomControl1.vb を開きます。

1. コントロールに組み込むカスタム メソッドやカスタム プロパティを実装します。

1. コントロールのグラフィカルな外観を変更する場合は、メソッドをオーバーライドし <xref:System.Windows.Forms.Control.OnPaint%2A> ます。

    > [!NOTE]
    > をオーバーライドし <xref:System.Windows.Forms.Control.OnPaint%2A> ても、すべてのコントロールの外観を変更することはできません。 Windows によって実行されるすべての描画 (たとえば、) を持つコントロールは、 <xref:System.Windows.Forms.TextBox> メソッドを呼び出すことがない <xref:System.Windows.Forms.Control.OnPaint%2A> ため、カスタムコードは使用されません。 メソッドが使用可能かどうかを確認するには、変更する特定のコントロールのヘルプドキュメントを参照してください <xref:System.Windows.Forms.Control.OnPaint%2A> 。 すべての Windows フォーム コントロールの一覧については、「[Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)」を参照してください。 コントロールがメンバーメソッドとしてリストされていない場合は <xref:System.Windows.Forms.Control.OnPaint%2A> 、このメソッドをオーバーライドすることによって外観を変更することはできません。 カスタム描画の詳細については、「[コントロールのカスタム描画およびレンダリング](custom-control-painting-and-rendering.md)」を参照してください。

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. コントロールを保存して、動作確認を行います。

## <a name="see-also"></a>関連項目

- [さまざまなカスタム コントロール](varieties-of-custom-controls.md)
- [方法: コントロール クラスを継承する](how-to-inherit-from-the-control-class.md)
- [方法: UserControl クラスを継承する](how-to-inherit-from-the-usercontrol-class.md)
- [方法: Windows フォームのコントロールを作成する](how-to-author-controls-for-windows-forms.md)
- [Visual Basic での継承されたイベント ハンドラーのトラブルシューティング](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [チュートリアル: Windows フォームコントロールからの継承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
