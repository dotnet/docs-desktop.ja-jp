---
title: フォームをプロジェクトに追加する
description: Visual Studio で .NET Windows フォーム プロジェクトに新しいフォームを追加する
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms, create add form
ms.openlocfilehash: fb35c1b62ca0b7a21581c350ddca7f21f45ec27f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942263"
---
# <a name="how-to-add-a-form-to-a-project-windows-forms-net"></a>プロジェクトにフォームを追加する方法 (Windows フォーム .NET)

Visual Studio でプロジェクトにフォームを追加します。 自分のアプリに複数のフォームがある場合は、自分のアプリのスタートアップ フォームを選択し、複数のフォームを同時に表示することができます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-a-new-form"></a>新しいフォームを追加する

Visual Studio で新しいフォームを追加します。

01. Visual Studio で **[プロジェクト エクスプローラー]** ウィンドウを見つけます。 プロジェクトを右クリックして、 **[追加]**  >  **[Form (Windows Forms)]\(フォーム (Windows フォーム)\)** を選択します。

    :::image type="content" source="media/how-to-add/right-click.png" alt-text="ソリューション エクスプローラーを右クリックして、Windows フォーム プロジェクトに新しいフォームを追加する":::

01. **[名前]** ボックスに、「*MyNewForm*」など、自分のフォームの名前を入力します。 Visual Studio では、使用可能な既定の一意の名前が用意されています。

    :::image type="content" source="media/how-to-add/new-form-dialog.png" alt-text="Visual Studio の Windows フォーム用の項目の追加ダイアログ":::

フォームを追加すると、Visual Studio によってそのフォーム用のフォーム デザイナーが開かれます。

## <a name="add-a-project-reference-to-a-form"></a>フォームにプロジェクト参照を追加する

フォームにソース ファイルがある場合は、プロジェクトと同じフォルダーにそれらのファイルをコピーし、プロジェクトにフォームを追加できます。 プロジェクトは、プロジェクトと同じフォルダーまたは子フォルダーにあるすべてのコード ファイルを自動的に参照します。

フォームは、_form2.cs_ (_form2_ はファイル名の例です) と _form2.Designer.cs_ の同じ名前の 2 つのファイルで構成されています。 同じ名前の (_form2.resx_) リソース ファイルが存在する場合もあります。 前の例の _form2_ は、ベースのファイル名です。 すべての関連ファイルをプロジェクト フォルダーにコピーします。

または、Visual Studio を使用して、プロジェクトにファイルをインポートします。 既存のファイルをプロジェクトに追加すると、ファイルはプロジェクトと同じフォルダーにコピーされます。

01. Visual Studio で **[プロジェクト エクスプローラー]** ウィンドウを見つけます。 プロジェクトを右クリックして、 **[編集]**  >  **[既存の項目]** を選択します。

    :::image type="content" source="media/how-to-add/existing-right-click.png" alt-text="ソリューション エクスプローラーを右クリックして、Windows フォーム プロジェクトに既存のフォームを追加する":::

02. 自分のフォーム ファイルを含むフォルダーに移動します。

03. _form2.cs_ ファイルを選択します。ここで _form2_ は、関連するフォーム ファイルのベース ファイル名です。 _form2.Designer.cs_ などのその他のファイルは選択しないでください。

## <a name="see-also"></a>関連項目

- [フォームの位置とサイズを設定する方法 (Windows フォーム .NET)](how-to-position-and-resize.md)
- [イベントの概要 (Windows フォーム .NET)](events.md)
- [コントロールの位置とレイアウト (Windows フォーム .NET)](../controls/layout.md)
