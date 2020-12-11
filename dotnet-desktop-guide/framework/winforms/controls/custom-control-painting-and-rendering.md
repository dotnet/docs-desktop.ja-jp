---
title: コントロールのカスタム描画およびレンダリング
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974246"
---
# <a name="custom-control-painting-and-rendering"></a>コントロールのカスタム描画およびレンダリング
コントロールのカスタム描画は、.NET Framework によって簡単に実行できる多数の複雑なタスクの1つです。 カスタムコントロールを作成する場合は、コントロールのグラフィカルな外観に関する多くのオプションがあります。 から継承されたコントロールを作成する場合は `Control` 、コントロールがグラフィック表示をレンダリングできるようにするコードを用意する必要があります。 を継承してユーザーコントロールを作成する場合、 `UserControl` またはいずれかの Windows フォームコントロールから継承する場合は、標準のグラフィック表示をオーバーライドし、独自のグラフィックスコードを提供することができます。 作成中のの構成コントロールにカスタムレンダリングを提供する場合 `UserControl` 、オプションの方が制限されますが、コントロールとアプリケーションに対してさまざまなグラフィカルな可能性があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Windows フォーム コントロールのレンダリング](rendering-a-windows-forms-control.md)  
 コントロールを表示するロジックをプログラミングする方法について説明します。  
  
 [ユーザー描画コントロール](user-drawn-controls.md)  
 コントロールのレンダリングコードを記述およびオーバーライドするために必要な手順の概要を示します。  
  
 [内在コントロール](constituent-controls.md)  
 ユーザーコントロールとフォームに内在コントロールのカスタムレンダリングコードを実装する方法について説明します。  
  
 [方法: 実行時にコントロールを非表示にする](how-to-make-your-control-invisible-at-run-time.md)  
 プロパティを使用し <xref:System.Windows.Forms.Control.Visible%2A> て、コントロールを非表示にしたり表示したりする方法について説明します。  
  
 [方法: コントロールに透明な背景を指定する](how-to-give-your-control-a-transparent-background.md)  
 メソッドを使用し <xref:System.Windows.Forms.Control.SetStyle%2A> て、不透明、透明、または部分的に透明な背景色を作成する方法について説明します。  
  
 [visual スタイルが使用されているコントロールのレンダリング](rendering-controls-with-visual-styles.md)  
 サポートされているオペレーティングシステムで、visual スタイルを使用してコントロールをレンダリングする方法を示します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.Control>  
 このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。  
  
 <xref:System.Windows.Forms.UserControl>  
 このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 このメソッドについて説明します。  
  
## <a name="related-sections"></a>関連項目  
 [方法: 描画する Graphics オブジェクトを作成する](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 Visual Studio の観点から GDI + グラフィックス機能を紹介し、詳細情報へのリンクを示します。  
  
 [さまざまなカスタム コントロール](varieties-of-custom-controls.md)  
 作成できるカスタムコントロールの種類について説明します。
