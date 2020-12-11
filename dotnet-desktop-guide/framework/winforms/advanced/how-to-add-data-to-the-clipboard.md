---
title: '方法: クリップボードにデータを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 0d9b82f01080d18353ecb91578a8005260bbe739
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974432"
---
# <a name="how-to-add-data-to-the-clipboard"></a>方法: クリップボードにデータを追加する

クラスには、 <xref:System.Windows.Forms.Clipboard> Windows オペレーティングシステムのクリップボード機能との対話に使用できるメソッドが用意されています。 多くのアプリケーションでは、データの一時リポジトリとしてクリップボードを使用します。 たとえば、ワードプロセッサは、切り取りと貼り付けの操作中にクリップボードを使用します。 クリップボードは、あるアプリケーションから別のアプリケーションにデータを転送する場合にも役立ちます。

クリップボードにデータを追加すると、他のアプリケーションがその形式を使用できる場合にデータを認識できるように、データ形式を指定できます。 また、データを複数の異なる形式でクリップボードに追加して、データを使用する可能性がある他のアプリケーションの数を増やすこともできます。

クリップボード形式は、その形式を使用するアプリケーションが関連データを取得できるように、形式を識別する文字列です。 クラスには、 <xref:System.Windows.Forms.DataFormats> 使用するための定義済みの形式名が用意されています。 独自の形式名を使用することも、形式としてオブジェクトの型を使用することもできます。

1つまたは複数の形式でクリップボードにデータを追加するには、メソッドを使用し <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> ます。 このメソッドには任意のオブジェクトを渡すことができますが、複数の形式でデータを追加するには、まず、複数の形式を使用するように設計された別のオブジェクトにデータを追加する必要があります。 通常は、にデータを追加します <xref:System.Windows.Forms.DataObject> が、インターフェイスを実装する任意の型を使用でき <xref:System.Windows.Forms.IDataObject> ます。

.NET Framework 2.0 では、基本的なクリップボードタスクを簡単にするために設計された新しいメソッドを使用して、クリップボードに直接データを追加できます。 テキストなどの1つの一般的な形式でデータを操作する場合は、これらのメソッドを使用します。

> [!NOTE]
> すべての Windows ベースのアプリケーションは、クリップボードを共有します。 そのため、別のアプリケーションに切り替えると、コンテンツが変更される可能性があります。
>
> クラスは、 <xref:System.Windows.Forms.Clipboard> シングルスレッドアパートメント (STA) モードに設定されているスレッドでのみ使用できます。 このクラスを使用するには、 `Main` メソッドが属性でマークされていることを確認し <xref:System.STAThreadAttribute> ます。
>
> オブジェクトをクリップボードに格納するには、オブジェクトをシリアル化できる必要があります。 型をシリアル化できるようにするには、属性を使用してマークし <xref:System.SerializableAttribute> ます。 シリアル化できないオブジェクトをクリップボードメソッドに渡すと、メソッドは例外をスローせずに失敗します。 シリアル化の詳細については、「<xref:System.Runtime.Serialization>」を参照してください。

### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>1つの一般的な形式でクリップボードにデータを追加するには

1. 、、 <xref:System.Windows.Forms.Clipboard.SetAudio%2A> <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A> <xref:System.Windows.Forms.Clipboard.SetImage%2A> 、またはメソッドを使用し <xref:System.Windows.Forms.Clipboard.SetText%2A> ます。 これらのメソッドは、.NET Framework 2.0 でのみ使用できます。

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>カスタム形式でクリップボードにデータを追加するには

1. <xref:System.Windows.Forms.Clipboard.SetData%2A>カスタム書式名を使用して、メソッドを使用します。 このメソッドは、.NET Framework 2.0 でのみ使用できます。

    メソッドでは、定義済みの書式名を使用することもでき <xref:System.Windows.Forms.Clipboard.SetData%2A> ます。 詳細については、「<xref:System.Windows.Forms.DataFormats>」を参照してください。

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>複数の形式でクリップボードにデータを追加するには

1. メソッドを使用 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> し、 <xref:System.Windows.Forms.DataObject> データが格納されているを渡します。 .NET Framework 2.0 より前のバージョンのクリップボードにデータを追加するには、このメソッドを使用する必要があります。

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>関連項目

- [ドラッグ アンド ドロップ操作とクリップボードのサポート](drag-and-drop-operations-and-clipboard-support.md)
- [方法: クリップボードからデータを取得する](how-to-retrieve-data-from-the-clipboard.md)
