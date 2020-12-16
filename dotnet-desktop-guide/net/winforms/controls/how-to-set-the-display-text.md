---
title: コントロールによって表示されるテキストを設定する
description: Windows フォーム コントロールによって表示されるテキストを設定する方法について説明します。 テキストを設定する、または返すには、Text プロパティを使用します。また、フォントを変更するには、Font プロパティを使用します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.openlocfilehash: 2fd5a62310ae5e7d6e0528c7f12f37ed40f8a626
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942194"
---
# <a name="how-to-set-the-text-displayed-by-a-control-windows-forms-net"></a>方法:コントロールによって表示されるテキストを設定する (Windows フォーム .NET)

Windows フォーム コントロールは、通常、コントロールの主な機能に関連するいくつかのテキストを表示します。 たとえば、<xref:System.Windows.Forms.Button> コントロールは、通常、ボタンがクリックされたときにどのようなアクションを実行するかを示すキャプションを表示します。 すべてのコントロールに対して、<xref:System.Windows.Forms.Control.Text%2A> プロパティを使用してテキストを設定または返すことができます。 <xref:System.Windows.Forms.Control.Font%2A> プロパティを使用して、フォントを変更することができます。

また、[デザイナー](#designer)を使用してテキストを設定することもできます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

01. Visual Studio の **プロパティ** ウィンドウで、コントロールの **Text** プロパティを適切な文字列に設定します。

    下線付きのショートカット キーを作成するには、ショートカット キーとなる文字の前にアンパサンド (&) を含めます。

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-text.png" alt-text=".NET Windows フォームの Text プロパティが表示された Visual Studio の [プロパティ] ペイン。":::

01. **プロパティ** ウィンドウで、**Font** プロパティの横にある省略記号ボタン (![Visual Studio のプロパティ ウィンドウの省略記号ボタン (...)](../media/visual-studio-ellipsis-button.png)) を選択します。

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-font.png" alt-text=".NET Windows フォームの Font プロパティが表示された Visual Studio の [プロパティ] ペイン。":::

    標準フォント ダイアログボックスで、種類、サイズ、スタイルなどの設定を使用してフォントを調整します。

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/font-window.png" alt-text=".NET Windows フォームの [フォント] 設定ウィンドウが表示された Visual Studio の [プロパティ] ペイン。":::

## <a name="programmatic"></a>プログラムによる

01. <xref:System.Windows.Forms.Control.Text%2A> プロパティを文字列に設定します。

    下線付きのアクセス キーを作成するには、アクセス キーにする文字の前にアンパサンド (&) を含めます。

01. <xref:System.Windows.Forms.Control.Font%2A> プロパティを型 <xref:System.Drawing.Font> のオブジェクトに設定します。

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    > [!NOTE]
    > エスケープ文字を使用すると、メニュー項目など、通常は別の解釈がなされるユーザー インターフェイス要素の特殊文字を表示できます。 たとえば、次のコード行は、メニュー項目のテキストが "& Now For Something Completely Different" と読めるように設定します。

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [方法 : Windows フォーム コントロールのアクセス キーを作成する](how-to-create-access-keys.md)
