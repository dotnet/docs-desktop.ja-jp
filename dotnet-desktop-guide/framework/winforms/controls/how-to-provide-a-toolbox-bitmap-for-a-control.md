---
title: '方法: コントロールにツールボックス ビットマップを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bb4ccc3b95dc69606a33074f21ee66aa5efda55b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974781"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>方法: コントロールにツールボックス ビットマップを指定する

コントロールの特殊なアイコンを Visual Studio の **ツールボックス** に表示する場合は、を使用して特定のイメージを指定でき <xref:System.Drawing.ToolboxBitmapAttribute> ます。 このクラスは "*属性*" であり、他のクラスに追加できる特殊なクラスです。 属性の詳細については、C# の Visual Basic または[属性 (C#)](/dotnet/csharp/programming-guide/concepts/attributes/index)の属性の概要に関する[トピック (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/attributes/index)を参照してください。

を使用 <xref:System.Drawing.ToolboxBitmapAttribute> すると、16 x 16 ピクセルのビットマップのパスとファイル名を示す文字列を指定できます。 コントロールを **ツールボックス** に追加すると、このビットマップがコントロールの横に表示されます。 また、を指定することもでき <xref:System.Type> ます。この場合、その型に関連付けられているビットマップが読み込まれます。 と文字列の両方を指定した場合 <xref:System.Type> 、コントロールは、パラメーターで指定された型を含むアセンブリ内の文字列パラメーターで指定された名前を持つイメージリソースを検索し <xref:System.Type> ます。

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>コントロールのツールボックス ビットマップを指定するには

1. <xref:System.Drawing.ToolboxBitmapAttribute> `Class` Visual Basic の場合はキーワード、visual C# の場合はクラス宣言の上に、コントロールのクラス宣言にを追加します。

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. プロジェクトをリビルドします。

    > [!NOTE]
    > ビットマップは、自動生成されたコントロールとコンポーネントのツールボックスには表示されません。 ビットマップを表示するには、**[ツールボックス アイテムの選択]** ダイアログ ボックスを使用してコントロールを再読み込みします。 詳細については、「[チュートリアル : ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [デザイン時の Windows フォーム コントロールの開発](developing-windows-forms-controls-at-design-time.md)
- [属性の概要 (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/attributes/index)
- [属性 (C#)](/dotnet/csharp/programming-guide/concepts/attributes/index)
