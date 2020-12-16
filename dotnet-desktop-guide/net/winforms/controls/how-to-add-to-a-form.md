---
title: フォームにコントロールを追加する
description: .NET 用の Windows フォームでコントロールをフォームに追加する方法について説明します
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.openlocfilehash: 44a20f135eb0f1503a6e5204a33aa8dca092123f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942287"
---
# <a name="add-a-control-windows-forms-net"></a>コントロールを追加する (Windows フォーム .NET)

ほとんどのフォームは、ユーザー インターフェイス (UI) を定義するために、フォームのサーフェイスにコントロールを追加して設計されます。 "*コントロール*" は、情報の表示やユーザー入力の受け入れに使用される、フォーム上のコンポーネントです。<!-- TODO For more information about controls, see [Forms overview](..\forms\overview.md). -->

コントロールをフォームに追加する主な方法としては、Visual Studio デザイナーを使用しますが、実行時にコードを使用して、フォーム上のコントロールを管理することもできます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-with-designer"></a>デザイナーを使用して追加する

Visual Studio でフォームをデザインするには、フォーム デザイナーを使用します。 [コントロール] ウィンドウが表示され、アプリで使用できるすべてのコントロールが一覧表示されます。 このウィンドウからコントロールを追加するには、2 つの方法があります。

### <a name="add-the-control-by-double-clicking"></a>ダブルクリックしてコントロールを追加する

コントロールをダブルクリックすると、既定の設定で、現在開いているフォームに自動的に追加されます。

:::image type="content" source="media/how-to-add-to-a-form/toolbox-double-click.gif" alt-text="Visual Studio for .NET の Windows フォームのツールボックスでコントロールをダブルクリックします":::

### <a name="add-the-control-by-drawing"></a>描画によってコントロールを追加する

コントロールをクリックして選択します。 フォームで領域をドラッグして選択します。 コントロールは、選択した領域のサイズに合わせて配置されます。

:::image type="content" source="media/how-to-add-to-a-form/toolbox-drag-draw.gif" alt-text="Visual Studio for .NET の Windows フォームのツールボックスからコントロールをドラッグして選択して、描画します":::

## <a name="add-with-code"></a>コードを使用して追加する

フォームの <xref:System.Windows.Forms.Control.Controls%2A> コレクションを使用して、コントロールを作成し、実行時にフォームに追加することができます。 また、このコレクションを使用して、フォームからコントロールを削除することもできます。

次のコードでは、[Label](xref:System.Windows.Forms.Label) と [TextBox](xref:System.Windows.Forms.TextBox) という 2 つのコントロールを追加して配置します。

:::code language="csharp" source="snippets/how-to-add-to-a-form/cs/Form1.cs" id="CreateControl":::

:::code language="vb" source="snippets/how-to-add-to-a-form/vb/Form1.vb" id="CreateControl":::

## <a name="see-also"></a>関連項目

- [方法 : Windows フォーム コントロールによって表示されるテキストを設定する](how-to-set-the-display-text.md)
- [方法: コントロールにアクセス キーのショートカットを追加する](how-to-create-access-keys.md)
- <xref:System.Windows.Forms.Label>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.Button>
