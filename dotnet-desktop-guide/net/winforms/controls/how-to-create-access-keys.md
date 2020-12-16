---
title: コントロールのアクセス キーを作成する
description: .NET 用の Windows フォームでコントロールまたはラベルにアクセス キーのショートカットを設定する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.openlocfilehash: 4d746082ffbaa749b882dcb1a769b5f9541c6fe8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942346"
---
# <a name="add-an-access-key-shortcut-to-a-control-windows-forms-net"></a>コントロールにアクセス キーのショートカットを追加する (Windows フォーム .NET)

"*アクセス キー*" は、メニュー、メニュー項目、またはボタンなどのコントロールのラベルのテキスト内の下線付きの文字です。 アクセス キーを使用すると、ユーザーは <kbd>Alt</kbd> キーを定義済みのアクセス キーと組み合わせて押すことで、ボタンを "クリック" できます。 たとえば、ボタンがフォームを印刷するプロシージャを実行することから、その `Text` プロパティが "Print" に設定されている場合、文字 "P" の前にアンパサンド (&) を追加すると、実行時にボタンのテキスト内の文字 "P" が下線付きで表示されます。 ユーザーは <kbd>Alt</kbd> キーを押すことで、ボタンに関連付けられているコマンドを実行できます。

フォーカスを受け取ることができないコントロールは、ラベル コントロールを除いてアクセス キーを持つことはできません。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

Visual Studio の **[プロパティ]** ウィンドウで、**Text** プロパティを、アクセス キーにする文字の前にアンパサンド (&) を含む文字列に設定します。 たとえば、文字 "P" をアクセス キーとして設定するには、「 **&Print**」と入力します。

:::image type="content" source="media/how-to-create-access-keys/properties-text.png" alt-text="Text プロパティが選択されアクセス キーが表示された [プロパティ] ダイアログ":::

## <a name="programmatic"></a>プログラムによる

`Text` プロパティを、ショートカットにする文字の前にアンパサンド (&) を含む文字列に設定します。

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

## <a name="use-a-label-to-focus-a-control"></a>ラベルを使用してコントロールにフォーカスを設定する

ラベルにフォーカスを設定することはできませんが、フォームのタブ オーダーで次のコントロールにフォーカスを設定する機能があります。 各コントロールには、<xref:System.Windows.Forms.Control.TabIndex> プロパティの値が (通常は昇順で) 割り当てられます。 アクセス キーが [Label.Text](xref:System.Windows.Forms.Label.Text) プロパティに割り当てられている場合、タブ オーダーで次のコントロールにフォーカスが移動します。

「[プログラムによる](#programmatic)」セクションの例を使用すると、ボタンに何もテキストが設定されておらず、代わりにプリンターの画像が表示されていた場合は、ラベルを使用してボタンにフォーカスを移動することができます。

```vb
' Set the letter "P" as an access key.
Label1.Text = "&Print"
Label1.TabIndex = 9
Button1.TabIndex = 10
```

```csharp
// Set the letter "P" as an access key.
label1.Text = "&Print";
label1.TabIndex = 9
button1.TabIndex = 10
```

## <a name="display-an-ampersand"></a>アンパサンドを表示する

アンパサンド (&) をアクセス キーとして解釈するコントロールのテキストまたはキャプションを設定する場合は、2 つの連続するアンパサンド (&&) を使用して、1 つのアンパサンドを表示します。 たとえば、`"Print && Close"` に設定されたボタンのテキストは、`Print & Close` のキャプションで表示されます。

```vb
' Set the letter "P" as an access key.
Button1.Text = "Print && Close"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "Print && Close";
```

:::image type="content" source="media/how-to-create-access-keys/double-ampersand.png" alt-text="ボタンにアンパサンドを表示する":::

## <a name="see-also"></a>関連項目

- [方法: Windows フォーム コントロールによって表示されるテキストを設定する](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.Label>
