---
title: '方法: visual スタイル要素を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: a2b9524b6a3e3c77d3c68c4d9e138b8c0e2a9373
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980723"
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="90046-102">方法: visual スタイル要素を描画する</span><span class="sxs-lookup"><span data-stu-id="90046-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="90046-103"><xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>名前空間は、 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> visual スタイルでサポートされている Windows ユーザーインターフェイス (UI) 要素を表すオブジェクトを公開します。</span><span class="sxs-lookup"><span data-stu-id="90046-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="90046-104">このトピックでは、クラスを使用して <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 、[ <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> スタート] メニューの [ **ログオフ** ] ボタンと [ **シャットダウン** ] ボタンを表すを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90046-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="90046-105">Visual スタイル要素を表示するには</span><span class="sxs-lookup"><span data-stu-id="90046-105">To render a visual style element</span></span>  
  
1. <span data-ttu-id="90046-106">を作成 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> し、描画する要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="90046-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="90046-107">プロパティとメソッドが使用されていることに注意してください <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> 。 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> visual スタイルが無効になっている場合、または要素が未定義の場合、コンストラクターは例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="90046-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. <span data-ttu-id="90046-108">メソッドを呼び出して <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> 、現在のが表す要素を表示 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> します。</span><span class="sxs-lookup"><span data-stu-id="90046-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="90046-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="90046-109">Compiling the Code</span></span>  
 <span data-ttu-id="90046-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="90046-110">This example requires:</span></span>  
  
- <span data-ttu-id="90046-111">クラスから派生したカスタムコントロール <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="90046-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="90046-112"><xref:System.Windows.Forms.Form>カスタムコントロールをホストする。</span><span class="sxs-lookup"><span data-stu-id="90046-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="90046-113"><xref:System?displayProperty=nameWithType>、、 <xref:System.Drawing?displayProperty=nameWithType> 、およびの各 <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="90046-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90046-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="90046-114">See also</span></span>

- [<span data-ttu-id="90046-115">visual スタイルが使用されているコントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="90046-115">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
