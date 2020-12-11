---
title: コントロール開発の基本
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: fab0a76e2f9fdb7e2f89e9d6a10dd9c522a6d8e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983800"
---
# <a name="windows-forms-control-development-basics"></a>Windows フォーム コントロール開発の基本概念
Windows フォームコントロールは、から直接または間接的に派生するクラスです <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。 Windows フォームコントロールを開発するための一般的なシナリオを次に示します。  
  
- 複合コントロールを作成するための既存のコントロールの組み合わせ。  
  
     複合コントロールは、コントロールとして再利用できるユーザーインターフェイスをカプセル化します。 複合コントロールの例としては、テキストボックスとリセットボタンで構成されるコントロールがあります。 ビジュアルデザイナーは、複合コントロールを作成するための豊富なサポートを提供します。 複合コントロールを作成するには、から派生させ <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> ます。 基本クラスは、 <xref:System.Windows.Forms.UserControl> 子コントロールのキーボードルーティングを提供し、子コントロールがグループとして機能できるようにします。 詳細については、「[複合 Windows フォーム コントロールの開発](developing-a-composite-windows-forms-control.md)」を参照してください。  
  
- 既存のコントロールを拡張してカスタマイズするか、機能を追加します。  
  
     色を変更できないボタンと、クリックされた回数を追跡する追加プロパティを持つボタンは、拡張コントロールの例です。 Windows フォームコントロールをカスタマイズするには、それから派生させ、プロパティ、メソッド、およびイベントをオーバーライドまたは追加します。  
  
- 既存のコントロールを結合または拡張しないコントロールを作成する。  
  
     このシナリオでは、基本クラスからコントロールを派生させ <xref:System.Windows.Forms.Control> ます。 を追加したり、基底クラスのプロパティ、メソッド、およびイベントをオーバーライドしたりすることができます。 作業を開始するには、「 [方法: 単純な Windows フォームコントロールを開発](how-to-develop-a-simple-windows-forms-control.md)する」を参照してください。  
  
 Windows フォームコントロールの基本クラスであるは、 <xref:System.Windows.Forms.Control> クライアント側の Windows ベースのアプリケーションで視覚的に表示するために必要な機能を提供します。 <xref:System.Windows.Forms.Control> ウィンドウハンドルを提供し、メッセージのルーティングを処理します。また、マウスイベントとキーボードイベント、およびその他の多くのユーザーインターフェイスイベントを提供します。 高度なレイアウトが提供され、、、、などのさまざまなビジュアル表示に固有のプロパティがあり <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> ます。 さらに、セキュリティ、スレッド処理のサポート、および ActiveX コントロールとの相互運用性が提供されます。 インフラストラクチャの大部分は基本クラスによって提供されるため、独自の Windows フォーム コントロールを比較的簡単に開発できます。  
  
## <a name="see-also"></a>関連項目

- [方法: シンプルな Windows フォーム コントロールを開発する](how-to-develop-a-simple-windows-forms-control.md)
- [複合 Windows フォーム コントロールの開発](developing-a-composite-windows-forms-control.md)
- [方法: 進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [さまざまなカスタム コントロール](varieties-of-custom-controls.md)
