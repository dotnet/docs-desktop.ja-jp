---
title: '方法: ウィンドウを開く'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985439"
---
# <a name="how-to-open-a-window"></a>方法: ウィンドウを開く
この例では、ウィンドウを開く方法を示します。  
  
## <a name="example"></a>例  
 ウィンドウを開くには、<xref:System.Windows.Window> をインスタンス化し、<xref:System.Windows.Window.Show%2A> メソッドを呼び出します。 ウィンドウを開いた <xref:System.Windows.Window.Show%2A> は、新しいウィンドウが閉じられるまで待たずにすぐに戻ります。 この種のウィンドウは "*モードレス*" ウィンドウとも呼ばれ、ユーザーの入力が制限されません。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 <xref:System.Windows.Window> をインスタンス化するには、アンセーフなネイティブ メソッドを呼び出すためのアクセス許可が必要です (<xref:System.Windows.Window.%23ctor%2A> に関する記事をご覧ください)。
