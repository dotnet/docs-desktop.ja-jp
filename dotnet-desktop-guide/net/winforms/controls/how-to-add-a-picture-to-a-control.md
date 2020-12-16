---
title: コントロールにイメージを表示する
description: Windows フォーム コントロールにイメージを表示する方法について説明します。 PictureBox などの多くのコントロールでは、イメージを表示することができます。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms contr ols
- examples [Windows Forms], controls
ms.openlocfilehash: a0b95d51f852df4c9ddc190903369faa41f7deae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942238"
---
# <a name="how-to-display-an-image-on-a-control-windows-forms-net"></a>コントロールにイメージを表示する方法 (Windows フォーム .NET)

いくつかの Windows フォーム コントロールでは、イメージを表示することができます。 これらのイメージは、Save コマンドを示すボタンのフロッピー ディスク アイコンなど、コントロールの目的を明確化するアイコンである場合があります。 または、コントロールの外観と動作を表す背景イメージである場合があります。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

Visual Studio の **[プロパティ]** ウィンドウで、コントロールの **Image** プロパティまたは **BackgroundImage** プロパティを選択し、省略記号 (![Visual Studio の省略記号ボタン](../media/visual-studio-ellipsis-button.png)) を選択して **[リソースの選択]** ダイアログ ボックスを表示し、表示するイメージを選択します。

:::image type="content" source="media/how-to-add-a-picture-to-a-control/properties-image.png" alt-text="image プロパティが選択されたプロパティ ダイアログ":::

## <a name="programmatic"></a>プログラムによる

コントロールの `Image` プロパティまたは `BackgroundImage` プロパティを <xref:System.Drawing.Image> 型のオブジェクトに設定します。 通常は、<xref:System.Drawing.Image.FromFile%2A> メソッドを使用して、ファイルからイメージを読み込みます。

次のコード例でイメージの場所として設定されているパスは、 **"マイ ピクチャ"** フォルダーです。 Windows オペレーティング システムが実行されているほとんどのコンピューターには、このディレクトリが含まれています。 これにより、システム アクセス レベルが最小限に設定されているユーザーも、アプリケーションを安全に実行できます。 次のコード例では、<xref:System.Windows.Forms.PictureBox> コントロールが追加済みのフォームが必要です。

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
