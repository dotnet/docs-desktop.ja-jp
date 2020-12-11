---
title: PrintDocument コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 96b18a44853d836cb0f16ba0e8372a825e998b74
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980554"
---
# <a name="printdocument-component-overview-windows-forms"></a>PrintDocument コンポーネントの概要 (Windows フォーム)

Windows フォーム [PrintDocument](printdocument-component-windows-forms.md) コンポーネントを使用して、印刷対象を示すプロパティを設定し、Windows ベースのアプリケーション内でドキュメントを印刷できます。 このコンポーネントは、ドキュメント印刷のあらゆる側面を制御するために、[PrintDialog](printdialog-component-windows-forms.md) コンポーネントと組み合わせて使用できます。

## <a name="working-with-the-printdocument-component"></a>PrintDocument コンポーネントの操作

コンポーネントに関連する主なシナリオは、次の2つです <xref:System.Drawing.Printing.PrintDocument> 。

- 簡易印刷ジョブ (個々のテキスト ファイルを印刷する場合など)。 このような場合は、コンポーネントを <xref:System.Drawing.Printing.PrintDocument> Windows フォームに追加し、イベントハンドラーでファイルを出力するプログラミングロジックを追加し <xref:System.Drawing.Printing.PrintDocument.PrintPage> ます。 プログラミングロジックは、 <xref:System.Drawing.Printing.PrintDocument.Print%2A> ドキュメントを印刷するメソッドとなする必要があります。 このメソッドは、 <xref:System.Drawing.Graphics> クラスのプロパティに含まれるオブジェクトを <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> <xref:System.Drawing.Printing.PrintPageEventArgs> プリンターに送信します。 コンポーネントを使用してテキストドキュメントを印刷する方法を示す例につい <xref:System.Drawing.Printing.PrintDocument> ては、「 [方法: Windows フォームで複数ページのテキストファイルを印刷](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)する」を参照してください。

- より複雑な印刷ジョブ (作成した印刷ロジックを再利用する場合など)。 このような場合は、コンポーネントから新しいコンポーネントを派生させ、 <xref:System.Drawing.Printing.PrintDocument> イベントを[](/dotnet/visual-basic/language-reference/modifiers/overrides)オーバーライドします (「C# の Visual Basic または[オーバーライド](/dotnet/csharp/language-reference/keywords/override)のオーバーライド」を参照してください) <xref:System.Drawing.Printing.PrintDocument.PrintPage> 。

フォームに追加されると、 <xref:System.Drawing.Printing.PrintDocument> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Windows フォームにおける印刷のサポート](../advanced/windows-forms-print-support.md)
- [PrintDocument コンポーネント](printdocument-component-windows-forms.md)
