---
title: '方法: ダイアログ ボックスを開く'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983440"
---
# <a name="how-to-open-a-dialog-box"></a>方法: ダイアログ ボックスを開く
この例では、ダイアログ ボックスを開く方法を示します。  
  
## <a name="example"></a>例  
 ダイアログ ボックスはウィンドウであり、<xref:System.Windows.Window> をインスタンス化して <xref:System.Windows.Window.ShowDialog%2A> メソッドを呼び出すことにより開かれます。 <xref:System.Windows.Window.ShowDialog%2A> では、ウィンドウが開かれた後、新しいダイアログ ボックスが閉じられるまでは制御は戻りません。 この種のウィンドウは "*モーダル*" ウィンドウとも呼ばれ、ユーザーの入力が制限されます。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 <xref:System.Windows.Window.ShowDialog%2A> を呼び出すには、すべてのウィンドウとユーザー入力イベントを無制限に使用するためのアクセス許可が必要です。  
  
## <a name="see-also"></a>関連項目

- [ダイアログ ボックスの結果を返す](how-to-return-a-dialog-box-result.md)
