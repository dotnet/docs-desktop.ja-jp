---
title: '方法: コントロールの描画クラスを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982792"
---
# <a name="how-to-use-a-control-rendering-class"></a>方法: コントロールの描画クラスを使用する
この例では、クラスを使用して <xref:System.Windows.Forms.ComboBoxRenderer> コンボボックスコントロールのドロップダウン矢印を表示する方法を示します。 この例は、 <xref:System.Windows.Forms.Control.OnPaint%2A> 単純なカスタムコントロールのメソッドで構成されています。 <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType>プロパティは、アプリケーションウィンドウのクライアント領域で visual スタイルが有効になっているかどうかを判断するために使用されます。 Visual スタイルがアクティブな場合、 <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> メソッドは visual スタイルを使用してドロップダウン矢印を表示します。それ以外の場合は、 <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> メソッドは従来の Windows スタイルでドロップダウン矢印を表示します。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- クラスから派生したカスタムコントロール <xref:System.Windows.Forms.Control> 。  
  
- <xref:System.Windows.Forms.Form>カスタムコントロールをホストする。  
  
- <xref:System?displayProperty=nameWithType>、、 <xref:System.Drawing?displayProperty=nameWithType> 、およびの各 <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 名前空間への参照。  
  
## <a name="see-also"></a>関連項目

- [visual スタイルが使用されているコントロールのレンダリング](rendering-controls-with-visual-styles.md)
