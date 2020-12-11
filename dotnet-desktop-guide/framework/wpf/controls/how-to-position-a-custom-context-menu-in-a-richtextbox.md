---
title: '方法: カスタム コンテキスト メニューを RichTextBox に配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985835"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="a6715-102">方法: カスタム コンテキスト メニューを RichTextBox に配置する</span><span class="sxs-lookup"><span data-stu-id="a6715-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="a6715-103">この例では、カスタム コンテキスト メニューを <xref:System.Windows.Controls.RichTextBox> に配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6715-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="a6715-104">**RichTextBox** のカスタム コンテキスト メニューを実装する場合、コンテキスト メニューの配置の処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6715-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="a6715-105">既定では、**RichTextBox** の中央でカスタム コンテキスト メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="a6715-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6715-106">例</span><span class="sxs-lookup"><span data-stu-id="a6715-106">Example</span></span>  
 <span data-ttu-id="a6715-107">既定の配置時の動作をオーバーライドするには、<xref:System.Windows.FrameworkContentElement.ContextMenuOpening> イベントのリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6715-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="a6715-108">次の例では、プログラムによってこれを実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a6715-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="a6715-109">例</span><span class="sxs-lookup"><span data-stu-id="a6715-109">Example</span></span>  
 <span data-ttu-id="a6715-110">次の例は、対応する <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> イベント リスナーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6715-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="a6715-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6715-111">See also</span></span>

- [<span data-ttu-id="a6715-112">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="a6715-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="a6715-113">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="a6715-113">TextBox Overview</span></span>](textbox-overview.md)
