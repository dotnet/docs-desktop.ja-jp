---
title: '方法: RichTextBox コントロール上にドロップしたファイルを開く'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: e3d0e9597b7ed69368f1755e146433d6e4bad9f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985016"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>方法: RichTextBox コントロール上にドロップしたファイルを開く

[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] では、<xref:System.Windows.Controls.TextBox>、<xref:System.Windows.Controls.RichTextBox>、および <xref:System.Windows.Documents.FlowDocument> のすべてのコントロールに、ドラッグ アンド ドロップ機能が組み込まれています。 組み込み機能を使用すると、コントロール内およびコントロール間でテキストをドラッグ アンド ドロップできるようになります。 ただし、コントロール上にファイルをドロップすることによってファイルを開くことはできません。 また、これらのコントロールでは、ドラッグ アンド ドロップ イベントが処理済みとしてマークされます。 結果として、既定では、ドロップされたファイルを開く機能を提供するための独自のイベント ハンドラーを追加することはできません。

これらのコントロールにドラッグ アンド ドロップ イベントの処理を追加するには、<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> メソッドを使用して、ドラッグ アンド ドロップ イベント用のイベント ハンドラーを追加します。 イベント ルート上の別の要素により既に処理済みとしてマークされているルーティング イベントに対し、指定したハンドラーが呼び出されるようにするには、`handledEventsToo` パラメーターを `true` に設定します。

> [!TIP]
> ドラッグ アンド ドロップ イベントのプレビューバージョンを処理し、プレビュー イベントを処理済みとしてマークすることによって、<xref:System.Windows.Controls.TextBox>、<xref:System.Windows.Controls.RichTextBox>、および <xref:System.Windows.Documents.FlowDocument> の組み込みのドラッグ アンド ドロップ機能を置き換えることができます。 ただし、これにより組み込みのドラッグ アンド ドロップ機能が無効になるため、推奨されません。

## <a name="example"></a>例

次の例は、<xref:System.Windows.Controls.RichTextBox> 上の <xref:System.Windows.DragDrop.DragOver> および <xref:System.Windows.DragDrop.Drop> イベントのハンドラーを追加する方法を示しています。 この例では、<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> メソッドを使用し、`handledEventsToo` パラメーターを `true` に設定することで、<xref:System.Windows.Controls.RichTextBox> でこれらのイベントが処理済みとしてマークされている場合でも、イベント ハンドラーが呼び出されるようにします。 イベント ハンドラーのコードにより、<xref:System.Windows.Controls.RichTextBox> にドロップされたテキスト ファイルを開くための機能が追加されます。

この例をテストするには、Windows エクスプローラーから <xref:System.Windows.Controls.RichTextBox> にテキスト ファイルまたはリッチ テキスト形式 (RTF) ファイルをドラッグします。 ファイルが <xref:System.Windows.Controls.RichTextBox> 内で開かれます。 ファイルをドロップする前に Shift キーを押すと、ファイルはプレーンテキストとして開かれます。

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
