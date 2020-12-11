---
title: PrintDialog コンポーネントを表示する方法
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980827"
---
# <a name="how-to-display-the-printdialog-component"></a>PrintDialog コンポーネントを表示する方法

<xref:System.Windows.Forms.PrintDialog>コンポーネントは、ユーザーの多くが使い慣れている標準の Windows 印刷ダイアログボックスです。 ユーザーはすぐに使いやすくなるため、コンポーネントを使用すると便利 <xref:System.Windows.Forms.PrintDialog> です。

## <a name="to-display-the-printdialog-component"></a>PrintDialog コンポーネントを表示するには

- <xref:System.Windows.Forms.Form.ShowDialog%2A>アプリケーションのコード内からメソッドを呼び出します。

     コンポーネントが表示されると、ユーザーはそれを使用して印刷ジョブのプロパティを設定します。 これらは、  <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> その印刷ジョブに関連付けられているクラス (およびユーザーがコンポーネントを介して [PageSetupDialog コンポーネント](pagesetupdialog-component-windows-forms.md) にアクセスする場合はクラス) に保存され <xref:System.Windows.Forms.PrintDialog> ます。 その後で、設定されたプロパティを呼び出して印刷ジョブの詳細を確認できます。

## <a name="see-also"></a>関連項目

- [方法: 標準の Windows フォーム印刷ジョブを作成する](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [方法: 実行時に PrintDialog のユーザー入力をキャプチャする](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [PrintPreviewDialog コントロール](printpreviewdialog-control-windows-forms.md)
- [PrintDialog コンポーネント](printdialog-component-windows-forms.md)
- [Windows フォームにおける印刷のサポート](../advanced/windows-forms-print-support.md)
- [Windows フォームコントロール](index.md)
