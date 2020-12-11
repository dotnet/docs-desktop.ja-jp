---
title: 単純なコントロールの開発
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: af8ba82cc5699a4b6a12eaf921dd9f4cbf3cecd1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980847"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>方法: シンプルな Windows フォーム コントロールを開発する

ここでは、カスタム Windows フォーム コントロールの主な作成手順を紹介します。 このチュートリアルで開発した単純なコントロールを使用すると、プロパティの配置 <xref:System.Windows.Forms.Control.Text%2A> を変更できます。 イベントを発生させたり処理したりすることはありません。

### <a name="to-create-a-simple-custom-control"></a>シンプルなカスタム コントロールを作成するには

1. <xref:System.Windows.Forms.Control?displayProperty=nameWithType> から派生するクラスを定義します。

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. プロパティを定義します  (プロパティを定義する必要はありません。コントロールはクラスから多くのプロパティを継承し <xref:System.Windows.Forms.Control> ますが、ほとんどのカスタムコントロールは通常、追加のプロパティを定義します)。次のコード片では、を `TextAlignment` 使用して、から継承された `FirstControl` プロパティの表示を書式設定するという名前のプロパティを定義し <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Control> ます。 プロパティの定義の詳細については、「[プロパティの概要](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120))」を参照してください。

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     コントロールのビジュアル表示を変更するプロパティを設定する場合は、メソッドを呼び出してコントロールを再描画する必要があり <xref:System.Windows.Forms.Control.Invalidate%2A> ます。 <xref:System.Windows.Forms.Control.Invalidate%2A> は、基本クラスで定義されて <xref:System.Windows.Forms.Control> います。

3. から継承されたプロテクトメソッドをオーバーライドし <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> て、レンダリングロジックをコントロールに提供します。 をオーバーライドしない場合 <xref:System.Windows.Forms.Control.OnPaint%2A> 、コントロール自体を描画することはできません。 次のコード片では、 <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドは、 <xref:System.Windows.Forms.Control.Text%2A> から継承されたプロパティと、 <xref:System.Windows.Forms.Control> フィールドで指定したアラインメントを表示し `alignmentValue` ます。

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. コントロールの属性を指定します。 ビジュアル デザイナーでは、デザイン時に属性を使用することで、コントロール、コントロールのプロパティ、およびイベントを適切に表示します。 次のコード フラグメントでは、属性が `TextAlignment` プロパティに適用されます。 Visual Studio などのデザイナーでは、 <xref:System.ComponentModel.CategoryAttribute.Category%2A> (コード片に示されている) 属性によって、プロパティが論理カテゴリの下に表示されます。 <xref:System.ComponentModel.DescriptionAttribute.Description%2A>属性を指定すると、プロパティが選択されたときに、説明的な文字列が [**プロパティ**] ウィンドウの下部に表示され `TextAlignment` ます。 属性の詳細については、「[コンポーネントのデザイン時属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))」を参照してください。

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. (省略可能) コントロールに対してリソースを指定します。 コントロールに対してビットマップなどのリソースを指定するには、コンパイラ オプション (C# の場合は `/res`) を使用して、リソースをコントロールと共にパッケージ化します。 実行時には、クラスのメソッドを使用してリソースを取得でき <xref:System.Resources.ResourceManager> ます。 リソースの作成と使用の詳細については、「[デスクトップ アプリケーションのリソース](/dotnet/framework/resources/index)」を参照してください。

6. コンパイルしてコントロールを配置します。 `FirstControl,` をコンパイルして配置するには、次の手順を実行します。

    1. 次のサンプル コードをソース ファイル (FirstControl.cs、FirstControl.vb など) に保存します。

    2. ソース コードをコンパイルして、アセンブリを生成し、アプリケーションのディレクトリに保存します。 それには、ソース ファイルが格納されているディレクトリで次のコマンドを実行します。

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         `/t:library` コンパイラ オプションは、作成しているアセンブリが (実行可能ファイルではなく) ライブラリであることをコンパイラに伝えます。 `/out` オプションでは、アセンブリの名前とパスを指定します。 `/r` オプションでは、コードが参照するアセンブリの名前を指定します。 この例では、ご自身のアプリケーションのみが使用できるプライベート アセンブリを作成します。 このため、アセンブリはご自身のアプリケーションのディレクトリに保存する必要があります。 配布用コントロールのパッケージ化と配置の詳細については、[配置](/dotnet/framework/deployment/index)に関するページをご覧ください。

次のサンプルは、`FirstControl` のコードを示しています。 このコントロールは、`CustomWinControls` 名前空間に囲まれています。 名前空間では、関連する型を論理的にグループ化できます。 コントロールは、新しい名前空間または既存の名前空間に作成できます。 C# では、`using` 宣言 (Visual Basic の場合は `Imports`) を使用すると、名前空間から型へアクセスするときに、型の完全修飾名を使用する必要はありません。 次の例では、 `using` 宣言によっ <xref:System.Windows.Forms.Control> て、 <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.Control> 完全修飾名を使用するのではなく、単純にからクラスにアクセスでき <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ます。

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>フォームでのカスタム コントロールの使用

`FirstControl` を使用するシンプルなフォームの例を次に示します。 この例では、`FirstControl` のインスタンスを 3 つ作成します。それぞれのインスタンスで、`TextAlignment` プロパティに異なる値が設定されます。

#### <a name="to-compile-and-run-this-sample"></a>このサンプルをコンパイルして実行するには

1. このサンプルをコンパイルして実行するには、次に示すサンプルのコードをソース ファイル (SimpleForm.cs または SimpleForms.vb) に保存します。

2. ソース ファイルが格納されているディレクトリから次のコマンドを実行して、ソース コードを実行可能アセンブリにコンパイルします。

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls.dll は、クラスを含むアセンブリです `FirstControl` 。 フォームがアセンブリにアクセスできるように、そのアセンブリはソース ファイル (SimpleForm.cs または SimpleForms.vb) と同じディレクトリに格納されている必要があります。

3. 次のコマンドで SimpleForm.exe を実行します。

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>関連項目

- [Windows フォーム コントロールのプロパティ](properties-in-windows-forms-controls.md)
- [Windows フォーム コントロールのイベント](events-in-windows-forms-controls.md)
