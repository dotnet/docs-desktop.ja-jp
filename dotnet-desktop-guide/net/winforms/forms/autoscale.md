---
title: フォームの自動スケーリング
description: .NET 用の Windows フォームでの UI のスケーリング処理について説明します。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.openlocfilehash: c414575c83723dc1930a0bfe298534eee9aa48c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942353"
---
# <a name="automatic-scaling-windows-forms-net"></a>自動スケーリング (Windows フォーム .NET)

自動スケーリングによって、特定のディスプレイの解像度またはフォントを持つマシンに合わせて設計されたフォームとコントロールを、ディスプレイの別の解像度やフォントを持つ別のマシンで適切に表示することができます。 フォームとコントロールが、ユーザーとその他の開発者のマシンのネイティブ ウィンドウとその他のアプリケーションで、一貫性を持つよう適切にサイズ変更され、 自動スケーリングと視覚スタイルにより、各ユーザーのマシンのネイティブの Windows アプリケーションと比較した場合、Windows フォーム アプリケーションが一貫したルック アンド フィールを維持することができます。

ほとんどの場合、自動スケーリングは Windows フォームで期待どおりに機能します。 ただし、フォント パターンの変更が問題になる可能性があります。<!-- TODO For an example of how to resolve this, see [How to: Respond to Font Scheme Changes in a Windows Forms Application](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md). -->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="need-for-automatic-scaling"></a>自動スケーリングの必要性

自動スケーリングがないと、1 つのディスプレイの解像度やフォントのために設計されたアプリケーションは、その解像度やフォントが変更されたときに、表示が小さすぎたり大きすぎたりします。 たとえば、アプリケーションが基準として Tahoma の 9 ポイントを使用して設計されている場合、調整なしでは、システム フォントが Tahoma の 12 ポイントのマシンで実行すると、表示が小さすぎます。 タイトル、メニュー、テキスト ボックスの内容などのテキストの要素は、他のアプリケーションより小さく表示されます。 さらに、タイトル バー、メニューや、多数のコントロールのテキストを含むユーザー インターフェイス (UI) 要素のサイズは、使用されるフォントに依存します。 この例では、これらの要素は比較的小さく表示されます。

類似する状況は、アプリケーションがディスプレイの特定の解像度のために設計されている場合にも発生します。 最も一般的な表示解像度は 96 ドット/インチ (DPI) (100% のディスプレイ スケーリングに相当) ですが、125%、150%、200% (それぞれ 120、144、192 DPI に相当) 以上をサポートするより高解像度なディスプレイも普及し始めています。 調整なしだと、特にグラフィックスに基づくアプリケーションで、ある解像度のために設計されたものが、別の解像度で実行したときに、表示が大きすぎたり小さすぎたりします。

自動スケーリングは、相対的なフォント サイズやディスプレイ解像度に従ってフォームと子コントロールを自動でサイズ変更することで、これらの問題に対処しようとしています。 Windows オペレーティング システムは、ダイアログ単位と呼ばれるは、相対的な測定単位を使用して、ダイアログ ボックスの自動スケーリングをサポートします。 ダイアログ単位は、システム フォントに基づいており、ピクセルとの関係は、Win32 SDK 関数 `GetDialogBaseUnits` によって決定できます。 ユーザーが Windows によって使用されるテーマを変更すると、すべてのダイアログ ボックスがそれに合わせて自動的に調整されます。 さらに、Windows フォームは、既定のシステム フォントまたはディスプレイの解像度のいずれかに応じて自動スケーリングをサポートしています。 必要に応じて、アプリケーションで自動スケーリングを無効化できます。

> [!CAUTION]
> DPI とフォントのスケーリング モードの任意の混在はサポートされません。 1 つのモード (DPI など) を使用してユーザー コントロールのスケールを調整し、別のモード (フォント) を使用してフォームに配置して問題が発生しない場合でも、基底フォームはあるモード、派生フォームは別のモードというように混在させると、予期しない結果が発生することがあります。

## <a name="automatic-scaling-in-action"></a>動作中の自動スケーリング

Windows フォームは、次のロジックを使用して、フォームとそのコンテンツを自動的にスケール調整します。

01. デザイン時に、各 <xref:System.Windows.Forms.ContainerControl> は <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> と <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> にそれぞれスケーリング モードと現在の解像度を記録します。

01. 実行時に、実際の解像度は <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> プロパティに格納されます。 <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A> プロパティは、実行時と設計時のスケーリング解像度の比率を動的に計算します。

01. フォームが読み込まれたときに、<xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> と <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> の値が異なる場合は、<xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> メソッドが呼び出されてコントロールと子のスケールを調整します。 このメソッドはレイアウトを中断し、<xref:System.Windows.Forms.Control.Scale%2A> メソッドを呼び出して実際のスケーリングを実行します。 その後、<xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> の値がプログレッシブ スケーリングを避けるために更新されます。

01. また、<xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> は次のような状況でも自動的に呼び出されます。

    - スケーリング モードが <xref:System.Windows.Forms.AutoScaleMode.Font> の場合の <xref:System.Windows.Forms.Control.OnFontChanged%2A> イベントへの応答。

    - コンテナー コントロールのレイアウトが再開され、<xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> プロパティまたは <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> プロパティで変更が検出されたとき。

    - 上記に示すように、親の <xref:System.Windows.Forms.ContainerControl> がスケーリングされたとき。 各コンテナー コントロールは、親コンテナーからのスケーリング ファクターではなく、独自のスケーリング ファクターを使用してその子のスケーリングを担当します。

01. 子コントロールは、いくつかの方法で、そのスケーリングの動作を変更できます。

    - <xref:System.Windows.Forms.Control.ScaleChildren%2A> プロパティをオーバーライドして、子コントロールをスケーリングすべきかどうかを決定することができます。

    - <xref:System.Windows.Forms.Control.GetScaledBounds%2A> メソッドをオーバーライドして、スケーリングのロジックではなく、コントロールがスケーリングされる両機にを調整することができます。

    - <xref:System.Windows.Forms.Control.ScaleControl%2A> メソッドをオーバーライドして、現在のコントロールのスケーリングのロジックを変更することができます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>

<!-- TODO
- [Rendering Controls with Visual Styles](controls/rendering-controls-with-visual-styles.md)
- [How to: Improve Performance by Avoiding Automatic Scaling](advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)-->
