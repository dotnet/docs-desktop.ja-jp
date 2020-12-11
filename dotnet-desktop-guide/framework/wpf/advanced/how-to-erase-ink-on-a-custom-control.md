---
title: '方法 : カスタム コントロールでインクを消去する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984671"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="1367b-102">方法 : カスタム コントロールでインクを消去する</span><span class="sxs-lookup"><span data-stu-id="1367b-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="1367b-103">は、 <xref:System.Windows.Ink.IncrementalStrokeHitTester> 現在描画されているストロークが別のストロークと交差するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1367b-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="1367b-104">これは <xref:System.Windows.Controls.InkCanvas> 、 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> がに設定されている場合にユーザーがを使用できるようにするコントロールを作成する場合に便利です <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint> 。</span><span class="sxs-lookup"><span data-stu-id="1367b-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1367b-105">例</span><span class="sxs-lookup"><span data-stu-id="1367b-105">Example</span></span>  
 <span data-ttu-id="1367b-106">次の例では、ユーザーがストロークの部分を消去できるようにするカスタムコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1367b-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="1367b-107">この例では、初期化時にインクを含むコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1367b-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="1367b-108">インクを収集するコントロールを作成する方法については、「 [インク入力コントロールの作成](creating-an-ink-input-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1367b-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
