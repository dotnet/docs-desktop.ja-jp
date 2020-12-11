---
title: '方法: カスタム レイアウト エンジンを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 8e5043e2b42b1e7449c6dab51691b6d57e28cd53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982480"
---
# <a name="how-to-implement-a-custom-layout-engine"></a>方法: カスタム レイアウト エンジンを実装する
次のコード例は、単純なフローレイアウトを実行するカスタムレイアウトエンジンを作成する方法を示しています。 という名前の panel コントロールを実装します。このコントロールは、プロパティをオーバーライドして `DemoFlowPanel` <xref:System.Windows.Forms.Control.LayoutEngine%2A> クラスのインスタンスを提供し `DemoFlowLayout` ます。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
