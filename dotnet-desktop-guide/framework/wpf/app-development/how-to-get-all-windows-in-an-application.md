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
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="f541a-102">方法: アプリケーションにすべてのウィンドウを取得する</span><span class="sxs-lookup"><span data-stu-id="f541a-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="f541a-103">この例では、アプリケーション内のすべての <xref:System.Windows.Window> オブジェクトを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f541a-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f541a-104">例</span><span class="sxs-lookup"><span data-stu-id="f541a-104">Example</span></span>  
 <span data-ttu-id="f541a-105">インスタンス化された <xref:System.Windows.Window> オブジェクトはすべて、表示されるかどうかにかかわらず、<xref:System.Windows.Application> によって管理されるウィンドウ参照のコレクションに自動的に追加され、<xref:System.Windows.Application.Windows%2A> から公開されます。</span><span class="sxs-lookup"><span data-stu-id="f541a-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="f541a-106">次のコードを使用して、<xref:System.Windows.Application.Windows%2A> を列挙することで、すべてのインスタンス化されたウィンドウを取得できます。</span><span class="sxs-lookup"><span data-stu-id="f541a-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
