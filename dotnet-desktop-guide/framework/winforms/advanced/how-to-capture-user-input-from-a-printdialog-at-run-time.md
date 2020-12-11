---
title: '方法: 実行時に PrintDialog のユーザー入力をキャプチャする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 2aaf988f362baf9cd80eb16e4a08f7f65a5077bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980083"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>方法: 実行時に PrintDialog のユーザー入力をキャプチャする
デザイン時に印刷に関連するオプションを設定することもできますが、ユーザーによって選択される可能性があるため、実行時にこれらのオプションを変更することが必要になる場合があります。 およびコンポーネントを使用して、ドキュメントを印刷するためのユーザー入力をキャプチャでき <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> ます。  
  
### <a name="to-change-print-options-programmatically"></a>印刷オプションをプログラムで変更するには  
  
1. <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> フォームにおよびコンポーネントを追加します。  
  
2. のプロパティを、 <xref:System.Windows.Forms.PrintDialog.Document%2A> <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> フォームに追加されたに設定します。  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. <xref:System.Windows.Forms.PrintDialog>メソッドを使用して、コンポーネントを表示し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. ダイアログからのユーザーの印刷オプションは、 <xref:System.Drawing.Printing.PrinterSettings> コンポーネントのプロパティにコピーされ <xref:System.Drawing.Printing.PrintDocument> ます。  
  
## <a name="see-also"></a>関連項目

- [方法: Windows フォームで複数ページのテキスト ファイルを印刷する](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Windows フォームにおける印刷のサポート](windows-forms-print-support.md)
