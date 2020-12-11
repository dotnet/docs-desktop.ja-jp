---
title: '方法: アプリケーションにすべてのウィンドウを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985440"
---
# <a name="how-to-get-all-windows-in-an-application"></a>方法: アプリケーションにすべてのウィンドウを取得する
この例では、アプリケーション内のすべての <xref:System.Windows.Window> オブジェクトを取得する方法を示します。  
  
## <a name="example"></a>例  
 インスタンス化された <xref:System.Windows.Window> オブジェクトはすべて、表示されるかどうかにかかわらず、<xref:System.Windows.Application> によって管理されるウィンドウ参照のコレクションに自動的に追加され、<xref:System.Windows.Application.Windows%2A> から公開されます。  
  
 次のコードを使用して、<xref:System.Windows.Application.Windows%2A> を列挙することで、すべてのインスタンス化されたウィンドウを取得できます。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
