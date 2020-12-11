---
title: フォームの継承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: d016eb52802a729ef3b41a1140cae3d64022d403
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981331"
---
# <a name="how-to-inherit-windows-forms"></a>方法: Windows フォームを継承する

新規の Windows フォームは、基本フォームから継承して簡単に複製できます。フォームが必要になるたびに、最初から作成し直す必要はありません。

デザイン時に **[継承ピッカー]** ダイアログ ボックスを使用してフォームを継承する方法、および継承されるコントロールのセキュリティ レベルを視覚的に区別する方法の詳細については、「[方法: [継承ピッカー] ダイアログ ボックスを使用してフォームを継承する](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)」を参照してください。

> [!NOTE]
> フォームを継承するには、そのフォームを含むファイルまたは名前空間が、実行可能ファイルまたは DLL に組み込まれている必要があります。 プロジェクトをビルドするには、**[ビルド]** メニューの **[ビルド]** を選択します。 また、フォームの継承先となるクラスに、名前空間への参照を追加する必要があります。

## <a name="inherit-a-form-programmatically"></a>プログラムによるフォームの継承

1. クラスに、継承元のフォームを含む名前空間への参照を追加します。

2. クラス定義に、継承元のフォームへの参照を追加します。 参照では、フォームを含んでいる名前空間を指定し、その後にピリオド、続いて基本フォーム自体の名前を指定します。

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 フォームを継承する場合は、イベント ハンドラーが 2 回呼び出されることで問題が発生する可能性があることに注意してください。これは、各イベントが基底クラスと継承クラスの両方によって処理されるためです。 この問題を回避する方法の詳細については、「[Visual Basic で継承されたイベント ハンドラーのトラブルシューティング](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)」を参照してください。

## <a name="see-also"></a>関連項目

- [Inherits ステートメント](/dotnet/visual-basic/language-reference/statements/inherits-statement)
- [Imports ステートメント (.NET 名前空間および型)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)
- [using](/dotnet/csharp/language-reference/keywords/using)
- [基本フォームの外観を変更した場合の影響](effects-of-modifying-base-form-appearance.md)
- [Windows フォームのビジュアルの継承](windows-forms-visual-inheritance.md)
