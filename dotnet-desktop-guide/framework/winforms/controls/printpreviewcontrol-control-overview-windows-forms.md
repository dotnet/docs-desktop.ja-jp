---
title: PrintPreviewControl コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983288"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>PrintPreviewControl コントロールの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.PrintPreviewControl> は、印刷時に表示される [PrintDocument](printdocument-component-windows-forms.md) を表示するために使用されます。 このコントロールには、ボタンやその他のユーザー インターフェイスの要素がないため、通常は、独自の印刷プレビューのユーザー インターフェイスを作成する場合にのみ <xref:System.Windows.Forms.PrintPreviewControl> を使用します。 標準ユーザーインターフェイスが必要な場合は、コントロールを使用し <xref:System.Windows.Forms.PrintPreviewDialog> てください。概要については、「 [Printプレビューダイアログコントロールの概要](printpreviewdialog-control-overview-windows-forms.md) 」を参照してください。  
  
## <a name="key-properties"></a>キー プロパティ  
 コントロールのキープロパティは <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> であり、プレビューするドキュメントを設定します。 ドキュメントはオブジェクトである必要があり <xref:System.Drawing.Printing.PrintDocument> ます。 印刷用のドキュメントの作成の概要については、「 [PrintDocument Component の概要](printdocument-component-overview-windows-forms.md) 」および「 [印刷サポートの Windows フォーム](../advanced/windows-forms-print-support.md)」を参照してください。 プロパティとプロパティによって、 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> コントロールで水平方向および垂直方向に表示されるページ数が決まります。 アンチエイリアシングを使用すると、テキストが滑らかに見えるようになりますが、表示速度が低下する可能性があります。これを使用するには、プロパティをに設定し <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> `true` ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PrintPreviewControl>
- [PrintPreviewDialog コントロールの概要](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl コントロール](printpreviewcontrol-control-windows-forms.md)
- [ダイアログ ボックス コントロールおよびコンポーネント](dialog-box-controls-and-components-windows-forms.md)
