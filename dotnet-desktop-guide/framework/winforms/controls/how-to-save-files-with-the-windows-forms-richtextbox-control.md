---
title: RichTextBox コントロールを使用してファイルを保存する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974750"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>方法: Windows フォームの RichTextBox コントロールを使用してファイルを保存する

Windows フォームコントロールは、 <xref:System.Windows.Forms.RichTextBox> 次のいずれかの形式で表示される情報を書き込むことができます。

- プレーンテキスト

- Unicode プレーンテキスト

- Rich-Text 形式 (RTF)

- OLE オブジェクトの代わりにスペースを含む RTF

- OLE オブジェクトのテキスト表現を含むプレーンテキスト

ファイルを保存するには、 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> メソッドを呼び出します。 **SaveFile** メソッドを使用して、データをストリームに保存することもできます。 詳細については、「<xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>」を参照してください。

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>コントロールの内容をファイルに保存するには

1. 保存するファイルのパスを決定します。

    実際のアプリケーションでこれを行うには、通常、コンポーネントを使用し <xref:System.Windows.Forms.SaveFileDialog> ます。 概要については、「 [Savefiledialog コンポーネントの概要](savefiledialog-component-overview-windows-forms.md)」を参照してください。

2. <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>保存するファイルと、必要に応じてファイルの種類を指定して、コントロールのメソッドを呼び出し <xref:System.Windows.Forms.RichTextBox> ます。 ファイル名を唯一の引数としてメソッドを呼び出すと、ファイルは RTF として保存されます。 別の種類のファイルを指定するには、2 番目の引数として <xref:System.Windows.Forms.RichTextBoxStreamType> 列挙型の値を指定します。

    次の例では、リッチテキストファイルの場所に設定されているパスが **[マイドキュメント** ] フォルダーです。 この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。 また、この場所を選択すると、最小限のシステムアクセスレベルのユーザーがアプリケーションを安全に実行できるようになります。 次の例では、フォームに <xref:System.Windows.Forms.RichTextBox> コントロールが既に追加されていることを前提としています。

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > 次のコード例では、ファイルが存在しない場合は新規にファイルを作成します。 アプリケーションでファイルを作成する必要がある場合、そのアプリケーションにはフォルダーの作成アクセスが必要です。 アクセス許可は、アクセス制御リストを使って設定します。 ファイルが既に存在する場合、アプリケーションに必要なのは、より低い特権である書き込みアクセスだけです。 可能な場合は、配置時にファイルを作成し、フォルダーのアクセスを作成するのではなく、1つのファイルに対する読み取りアクセスのみを許可する方が安全です。 また、ルート フォルダーや Program Files フォルダーにデータを書き込むよりも、ユーザー フォルダーに書き込む方が安全です。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox コントロール](richtextbox-control-windows-forms.md)
- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
