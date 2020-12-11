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
# <a name="how-to-open-a-window"></a><span data-ttu-id="8f12c-102">方法: ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="8f12c-102">How to: Open a Window</span></span>
<span data-ttu-id="8f12c-103">この例では、ウィンドウを開く方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f12c-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f12c-104">例</span><span class="sxs-lookup"><span data-stu-id="8f12c-104">Example</span></span>  
 <span data-ttu-id="8f12c-105">ウィンドウを開くには、<xref:System.Windows.Window> をインスタンス化し、<xref:System.Windows.Window.Show%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f12c-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="8f12c-106">ウィンドウを開いた <xref:System.Windows.Window.Show%2A> は、新しいウィンドウが閉じられるまで待たずにすぐに戻ります。</span><span class="sxs-lookup"><span data-stu-id="8f12c-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="8f12c-107">この種のウィンドウは "*モードレス*" ウィンドウとも呼ばれ、ユーザーの入力が制限されません。</span><span class="sxs-lookup"><span data-stu-id="8f12c-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="8f12c-108">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8f12c-108">.NET Framework Security</span></span>  
 <span data-ttu-id="8f12c-109"><xref:System.Windows.Window> をインスタンス化するには、アンセーフなネイティブ メソッドを呼び出すためのアクセス許可が必要です (<xref:System.Windows.Window.%23ctor%2A> に関する記事をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="8f12c-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
