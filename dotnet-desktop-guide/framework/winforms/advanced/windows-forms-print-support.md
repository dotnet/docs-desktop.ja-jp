---
title: 印刷のサポート
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981135"
---
# <a name="windows-forms-print-support"></a>Windows フォームにおける印刷のサポート
Windows フォームでの印刷は、主に [PrintDocument コンポーネント](../controls/printdocument-component-windows-forms.md) コンポーネントを使用してユーザーを印刷できるようにし、 [printPageSetupDialog dialog Control](../controls/printpreviewdialog-control-windows-forms.md) コントロール、 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md) 、および [コンポーネント](../controls/pagesetupdialog-component-windows-forms.md) コンポーネントを使用して、Windows オペレーティングシステムに慣れているユーザーに使い慣れたグラフィカルインターフェイスを提供します。  
  
 通常は、コンポーネントの新しいインスタンスを作成し <xref:System.Drawing.Printing.PrintDocument> 、クラスとクラスを使用して、印刷する内容を示すプロパティを設定 <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> します。次に、メソッドを呼び出して、 <xref:System.Drawing.Printing.PrintDocument.Print%2A> ドキュメントを実際に印刷します。  
  
 Windows ベースのアプリケーションから印刷する過程で、コンポーネントには、印刷 <xref:System.Drawing.Printing.PrintDocument> が行われていること、および印刷ジョブをキャンセルできることをユーザーに通知する [中止印刷] ダイアログボックスが表示されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: 標準の Windows フォーム印刷ジョブを作成する](how-to-create-standard-windows-forms-print-jobs.md)  
 コンポーネントを使用して Windows フォームから印刷する方法について説明し <xref:System.Drawing.Printing.PrintDocument> ます。  
  
 [方法: 実行時に PrintDialog のユーザー入力をキャプチャする](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 コンポーネントを使用して、選択した印刷オプションをプログラムで変更する方法について説明し <xref:System.Windows.Forms.PrintDialog> ます。  
  
 [方法: Windows フォームでユーザーのコンピューターに接続されたプリンターを選択する](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 実行時にコンポーネントを使用して印刷するようにプリンターを変更する方法について説明し <xref:System.Windows.Forms.PrintDialog> ます。  
  
 [方法: Windows フォームでグラフィックスを印刷する](how-to-print-graphics-in-windows-forms.md)  
 プリンターへのグラフィックスの送信について説明します。  
  
 [方法: Windows フォームで複数ページのテキスト ファイルを印刷する](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 プリンターにテキストを送信する方法について説明します。  
  
 [方法: Windows フォームの印刷ジョブを完了する](how-to-complete-windows-forms-print-jobs.md)  
 印刷ジョブの完了をユーザーに通知する方法について説明します。  
  
 [方法: Windows フォームを印刷する](how-to-print-a-windows-form.md)  
 現在のフォームのコピーを印刷する方法について説明します。  
  
 [方法: Windows フォームで印刷プレビューを使用して印刷する](how-to-print-in-windows-forms-using-print-preview.md)  
 を使用してドキュメントを印刷する方法について説明し <xref:System.Windows.Forms.PrintPreviewDialog> ます。  
  
## <a name="related-sections"></a>関連項目  
 [PrintDocument コンポーネント](../controls/printdocument-component-windows-forms.md)  
 コンポーネントの使用方法について説明 <xref:System.Drawing.Printing.PrintDocument> します。  
  
 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md)  
 コンポーネントの使用方法について説明 <xref:System.Windows.Forms.PrintDialog> します。  
  
 [PrintPreviewDialog コントロール](../controls/printpreviewdialog-control-windows-forms.md)  
 コントロールの使用方法について説明 <xref:System.Windows.Forms.PrintPreviewDialog> します。  
  
 [PageSetupDialog コンポーネント](../controls/pagesetupdialog-component-windows-forms.md)  
 コンポーネントの使用方法について説明 <xref:System.Windows.Forms.PageSetupDialog> します。  
  
 <xref:System.Drawing.Printing>  
 名前空間のクラスについて説明し <xref:System.Drawing.Printing> ます。
