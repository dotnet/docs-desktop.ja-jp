---
title: '方法: Enter キーが押されたことを検出する'
description: Windows Presentation Foundation でキーボードの Enter キーが選択されていることを検出します。 この例は、XAML と分離コード ファイルで構成されています。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: 1e74113f22e03f41da2e51178179aa52f6bfcd2c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983519"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="c6a2b-104">方法: Enter キーが押されたことを検出する</span><span class="sxs-lookup"><span data-stu-id="c6a2b-104">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="c6a2b-105">この例では、キーボードで <xref:System.Windows.Input.Key.Enter> キーが押されたことを検出する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6a2b-105">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="c6a2b-106">この例は、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルと分離コード ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c6a2b-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6a2b-107">例</span><span class="sxs-lookup"><span data-stu-id="c6a2b-107">Example</span></span>  
 <span data-ttu-id="c6a2b-108">ユーザーが <xref:System.Windows.Controls.TextBox> で <xref:System.Windows.Input.Key.Enter> キーを押すと、テキスト ボックス内の入力が[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] の別の領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6a2b-108">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="c6a2b-109">次の XAML では、<xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.TextBlock>、および <xref:System.Windows.Controls.TextBox> で構成されるユーザー インターフェイスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c6a2b-109">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="c6a2b-110">次の分離コードでは、<xref:System.Windows.UIElement.KeyDown> イベント ハンドラーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c6a2b-110">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="c6a2b-111">押されたキーが <xref:System.Windows.Input.Key.Enter> キーの場合、<xref:System.Windows.Controls.TextBlock> にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6a2b-111">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="c6a2b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6a2b-112">See also</span></span>

- [<span data-ttu-id="c6a2b-113">入力の概要</span><span class="sxs-lookup"><span data-stu-id="c6a2b-113">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="c6a2b-114">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="c6a2b-114">Routed Events Overview</span></span>](routed-events-overview.md)
