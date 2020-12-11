---
title: '方法: クリップボードからデータを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: ca24615049abcc145698c033f31e6c98a38253bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981288"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>方法: クリップボードからデータを取得する

クラスには、 <xref:System.Windows.Forms.Clipboard> Windows オペレーティングシステムのクリップボード機能との対話に使用できるメソッドが用意されています。 多くのアプリケーションでは、データの一時リポジトリとしてクリップボードを使用します。 たとえば、ワードプロセッサは、切り取りと貼り付けの操作中にクリップボードを使用します。 クリップボードは、アプリケーション間で情報を転送する場合にも役立ちます。

アプリケーションによっては、データを複数の形式でクリップボードに格納することで、データを使用する可能性のある他のアプリケーションの数を増やすことができます。 クリップボード形式は、形式を識別する文字列です。 識別された形式を使用するアプリケーションは、クリップボードにある関連データを取得できます。 クラスには、 <xref:System.Windows.Forms.DataFormats> 使用するための定義済みの形式名が用意されています。 独自の形式名を使用することも、形式としてオブジェクトの型を使用することもできます。 クリップボードにデータを追加する方法については、「 [方法: クリップボードにデータを追加](how-to-add-data-to-the-clipboard.md)する」を参照してください。

クリップボードに特定の形式のデータが含まれているかどうかを確認するには、いずれかの `Contains` *書式* メソッドまたはメソッドを使用し <xref:System.Windows.Forms.Clipboard.GetData%2A> ます。 クリップボードからデータを取得するには、いずれかの `Get` *書式* メソッドまたはメソッドを使用し <xref:System.Windows.Forms.Clipboard.GetData%2A> ます。 これらのメソッドは .NET Framework 2.0 で新しく追加されたものです。

.NET Framework 2.0 より前のバージョンを使用してクリップボードのデータにアクセスするには、メソッドを使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> して、返されるのメソッドを呼び出し <xref:System.Windows.Forms.IDataObject> ます。 たとえば、返されたオブジェクトで特定の形式が使用可能かどうかを判断するには、メソッドを呼び出し <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> ます。

> [!NOTE]
> すべての Windows ベースのアプリケーションは、システムクリップボードを共有します。 そのため、別のアプリケーションに切り替えると、コンテンツが変更される可能性があります。
>
> クラスは、 <xref:System.Windows.Forms.Clipboard> シングルスレッドアパートメント (STA) モードに設定されているスレッドでのみ使用できます。 このクラスを使用するには、 `Main` メソッドが属性でマークされていることを確認し <xref:System.STAThreadAttribute> ます。

### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>1つの共通形式でクリップボードからデータを取得するには

1. 、、 <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A> <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A> <xref:System.Windows.Forms.Clipboard.GetImage%2A> 、またはメソッドを使用し <xref:System.Windows.Forms.Clipboard.GetText%2A> ます。 必要に応じて、対応する書式メソッドを使用して、 `Contains` データを特定の形式で使用できるかどうかを判断します。 これらのメソッドは、.NET Framework 2.0 でのみ使用できます。

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>カスタム形式でクリップボードからデータを取得するには

1. <xref:System.Windows.Forms.Clipboard.GetData%2A>カスタム書式名を使用して、メソッドを使用します。 このメソッドは、.NET Framework 2.0 でのみ使用できます。

    メソッドでは、定義済みの書式名を使用することもでき <xref:System.Windows.Forms.Clipboard.SetData%2A> ます。 詳細については、「<xref:System.Windows.Forms.DataFormats>」を参照してください。

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>複数の形式でクリップボードからデータを取得するには

1. <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> メソッドを使用します。 .NET Framework 2.0 より前のバージョンのクリップボードからデータを取得するには、このメソッドを使用する必要があります。

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>関連項目

- [ドラッグ アンド ドロップ操作とクリップボードのサポート](drag-and-drop-operations-and-clipboard-support.md)
- [方法: クリップボードにデータを追加する](how-to-add-data-to-the-clipboard.md)
