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
# <a name="how-to-render-a-visual-style-element"></a>方法: visual スタイル要素を描画する
<xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>名前空間は、 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> visual スタイルでサポートされている Windows ユーザーインターフェイス (UI) 要素を表すオブジェクトを公開します。 このトピックでは、クラスを使用して <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 、[ <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> スタート] メニューの [ **ログオフ** ] ボタンと [ **シャットダウン** ] ボタンを表すを表示する方法について説明します。  
  
### <a name="to-render-a-visual-style-element"></a>Visual スタイル要素を表示するには  
  
1. を作成 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> し、描画する要素に設定します。 プロパティとメソッドが使用されていることに注意してください <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> 。 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> visual スタイルが無効になっている場合、または要素が未定義の場合、コンストラクターは例外をスローします。  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. メソッドを呼び出して <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> 、現在のが表す要素を表示 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> します。  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- クラスから派生したカスタムコントロール <xref:System.Windows.Forms.Control> 。  
  
- <xref:System.Windows.Forms.Form>カスタムコントロールをホストする。  
  
- <xref:System?displayProperty=nameWithType>、、 <xref:System.Drawing?displayProperty=nameWithType> 、およびの各 <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 名前空間への参照。  
  
## <a name="see-also"></a>関連項目

- [visual スタイルが使用されているコントロールのレンダリング](rendering-controls-with-visual-styles.md)
