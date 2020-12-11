---
title: 印刷ジョブの完了
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975013"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>方法: Windows フォームの印刷ジョブを完了する
多くの場合、印刷を伴うワードプロセッサやその他のアプリケーションには、印刷ジョブが完了したことをユーザーに示すオプションが用意されています。 コンポーネントのイベントを処理することによって、この機能を Windows フォームに提供でき <xref:System.Drawing.Printing.PrintDocument.EndPrint> <xref:System.Drawing.Printing.PrintDocument> ます。  
  
 次の手順では、windows ベースのアプリケーションからの印刷を有効にするための標準的な方法であるコンポーネントを含む Windows ベースのアプリケーションを作成しておく必要があり <xref:System.Drawing.Printing.PrintDocument> ます。 コンポーネントを使用した Windows フォームからの印刷の詳細につい <xref:System.Drawing.Printing.PrintDocument> ては、「 [方法: 標準 Windows フォーム印刷ジョブを作成](how-to-create-standard-windows-forms-print-jobs.md)する」を参照してください。  
  
### <a name="to-complete-a-print-job"></a>印刷ジョブを完了するには  
  
1. <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>コンポーネントのプロパティを設定 <xref:System.Drawing.Printing.PrintDocument> します。  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <xref:System.Drawing.Printing.PrintDocument.EndPrint> イベントを処理するコードを記述します。  
  
     次のコード例では、ドキュメントの印刷が完了したことを示すメッセージボックスが表示されます。  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual C# および Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows フォームにおける印刷のサポート](windows-forms-print-support.md)
