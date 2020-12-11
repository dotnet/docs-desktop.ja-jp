---
title: PrintPreviewDialog コントロールの概要
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: c7576beb56cd10a691a850969c132a2d33ad8870
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974395"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Printプレビューダイアログコントロールの概要 (Windows フォーム)

Windows フォーム <xref:System.Windows.Forms.PrintPreviewDialog> コントロールは、印刷時の [PrintDocument](printdocument-component-windows-forms.md) の表示方法を表示するために事前に構成されたダイアログボックスです。 独自のダイアログボックスを構成するのではなく、単純なソリューションとして Windows ベースのアプリケーション内で使用します。 このコントロールには、印刷を開始するボタン、ズーム イン用のボタン、1 ページまたは複数ページを表示するボタン、およびダイアログ ボックスを閉じるためのボタンが含まれています。

## <a name="key-properties-and-methods"></a>キーのプロパティとメソッド

コントロールのキープロパティは <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> であり、プレビューするドキュメントを設定します。 ドキュメントはオブジェクトである必要があり <xref:System.Drawing.Printing.PrintDocument> ます。 ダイアログボックスを表示するには、メソッドを呼び出す必要があり <xref:System.Windows.Forms.Form.ShowDialog%2A> ます。 アンチエイリアシングを使用すると、テキストを滑らかに表示できますが、表示速度が低下することもあります。これを使用するには、プロパティをに設定し <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> `true` ます。

特定のプロパティは、に格納されているを介して使用でき <xref:System.Windows.Forms.PrintPreviewControl> <xref:System.Windows.Forms.PrintPreviewDialog> ます。 (フォームにこのを追加する必要はありません <xref:System.Windows.Forms.PrintPreviewControl> 。フォームにダイアログを追加すると、に自動的に含まれ <xref:System.Windows.Forms.PrintPreviewDialog> ます)。で使用できるプロパティの例 <xref:System.Windows.Forms.PrintPreviewControl> <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> として、プロパティとプロパティがあり <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> ます。このプロパティは、コントロールの水平方向および垂直方向に表示されるページ数を決定します。 プロパティには <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> `PrintPreviewDialog1.PrintPreviewControl.Columns` 、Visual Basic、 `printPreviewDialog1.PrintPreviewControl.Columns` Visual C#、または Visual C++ でアクセスでき `printPreviewDialog1->PrintPreviewControl->Columns` ます。

## <a name="printpreviewdialog-performance"></a>Printプレビューダイアログのパフォーマンス

次の条件下では、 <xref:System.Windows.Forms.PrintPreviewDialog> コントロールの初期化が非常に遅くなります。

- ネットワークプリンターが使用されます。
- このプリンターのユーザー設定 (二重設定など) は変更されます。

.NET Framework 4.5.2 で実行されているアプリでは、構成ファイルのセクションに次のキーを追加して、 \<appSettings> コントロールの初期化のパフォーマンスを向上させることができ <xref:System.Windows.Forms.PrintPreviewDialog> ます。

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

`EnablePrintPreviewOptimization`キーが他の値に設定されている場合、またはキーが存在しない場合は、最適化は適用されません。

.NET Framework 4.6 以降のバージョンで実行されているアプリでは、 [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) アプリ構成ファイルのセクションで次のスイッチを要素に追加できます。

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

スイッチが存在しない場合、または他の値に設定されている場合、最適化は適用されません。

イベントを使用して <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> プリンターの設定を変更した場合、 <xref:System.Windows.Forms.PrintPreviewDialog> 最適化構成スイッチが設定されていても、コントロールのパフォーマンスは向上しません。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [PrintPreviewControl コントロールの概要](printpreviewcontrol-control-overview-windows-forms.md)
- [PrintPreviewDialog コントロール](printpreviewdialog-control-windows-forms.md)
- [ダイアログ ボックス コントロールおよびコンポーネント](dialog-box-controls-and-components-windows-forms.md)
