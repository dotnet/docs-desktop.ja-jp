---
title: フォームとコントロールの国際対応フォント
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981211"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Windows フォームとコントロールの国際対応フォント

国際対応のアプリケーションでは、可能な限りフォントフォールバックを使用することをお勧めします。 フォントフォールバックとは、文字が属するスクリプトをシステムが決定することを意味します。

## <a name="using-font-fallback"></a>フォントフォールバックの使用

この機能を利用するに <xref:System.Drawing.Font> は、フォームまたは他の要素のプロパティを設定しないでください。 アプリケーションは、オペレーティングシステムのローカライズされた言語とは異なる既定のシステムフォントを自動的に使用します。 アプリケーションを実行すると、オペレーティングシステムで選択されているカルチャに対応する正しいフォントがシステムによって自動的に提供されます。

フォントを設定しないという規則には例外があります。これは、フォントスタイルを変更するためのものです。 これは、ユーザーがボタンをクリックしてテキストボックス内のテキストを太字で表示するアプリケーションにとって重要な場合があります。 これを行うには、フォームのフォントの内容に基づいて、テキストボックスのフォントスタイルを太字に変更する関数を記述します。 この関数は、ボタンの <xref:System.Windows.Forms.Control.Click> イベントハンドラーとイベントハンドラーの2か所で呼び出すことが重要です <xref:System.Windows.Forms.Control.FontChanged> 。 関数がイベントハンドラーでのみ呼び出され、 <xref:System.Windows.Forms.Control.Click> 他の一部のコードがフォーム全体のフォントファミリを変更した場合、テキストボックスはフォームの他の部分では変更されません。

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

ただし、アプリケーションをローカライズするときに、特定の言語で太字のフォントが正しく表示されない場合があります。 この問題が懸念される場合は、フォントを太字から標準テキストに切り替えるオプションをローカライザーに与えることをお勧めします。 ローカライザーは通常開発者ではなく、ソースコードにアクセスできないため、リソースファイルにのみアクセスできます。このオプションはリソースファイルで設定する必要があります。 これを行うには、プロパティを <xref:System.Drawing.Font.Bold%2A> に設定し `true` ます。 これにより、ローカライズ可能なリソースファイルにフォント設定が書き込まれます。 次に、メソッドの後にコードを記述し `InitializeComponent` て、フォームのフォントに基づいてフォントをリセットします。ただし、リソースファイルに指定されているフォントスタイルを使用します。

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>関連項目

- [フォントとテキストの使用](using-fonts-and-text.md)
