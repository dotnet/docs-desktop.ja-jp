---
title: カスタム コントロールの種類
description: .NET 用の Windows フォームで作成できるさまざまな種類のカスタム コントロールについて説明します。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- UserControl
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 25430adf6efbb4c1f323496ce46cdea5aa0bb95c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942274"
---
# <a name="types-of-custom-controls-windows-forms-net"></a>カスタム コントロールの種類 (Windows フォーム .NET)

Windows フォームを使用して、新しいコントロールを開発し、実装できます。 新しいユーザー コントロールを作成し、継承によって既存のコントロールを変更し、独自のペインティングを実行するカスタム コントロールを作成することができます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

作成するコントロールの種類を決めるときに、判断に迷うことがあります。 この記事では、継承できる各種コントロールの違いを示し、プロジェクトに合わせて特定のタイプのコントロールを選択する方法について説明します。

<table>
<thead>
  <tr>
    <th>次の場合</th>
    <th>作成するもの</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>
        <ul>
            <li>いくつかの Windows フォーム コントロールの機能を再利用可能な 1 つの単位に結合します。</li>
        </ul>
    </td>
    <td><a href="#composite-controls">複合コントロール</a>。<a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a> から継承します。</td>
  </tr>
  <tr>
    <td>
        <ul>
            <li>必要とする機能のほとんどが、既存の Windows フォーム コントロールと同じです。</li>
            <li>カスタムのグラフィカル ユーザー インターフェイスが不要な場合、または既存のコントロールの新しいグラフィカル ユーザー インターフェイスをデザインする場合。</li>
        </ul>
    </td>
    <td><a href="#extended-controls">拡張コントロール</a>。特定の Windows フォーム コントロールから継承します。</td>
  </tr>
  <tr>
    <td>
        <ul>
            <li>コントロールのカスタムのグラフィカル表現を提供します。</li>
            <li>標準コントロールでは使用できないカスタムの機能を実装する必要があります。</li>
        </ul>
    </td>
    <td><a href="#custom-controls">カスタム コントロール</a>。<a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a> から継承します。</td>
  </tr>
</tbody>
</table>

## <a name="base-control-class"></a>基本コントロール クラス

<xref:System.Windows.Forms.Control> クラスは、Windows フォーム コントロールの基底クラスです。 Windows フォーム アプリケーションでのビジュアル表示に必要なインフラストラクチャが提供され、さらに以下の機能が提供されます。

- ウィンドウ ハンドルを公開する。
- メッセージ ルーティングを管理する。
- マウス イベントとキーボード イベント、および他のさまざまなユーザー インターフェイス イベントを提供する。
- 高度なレイアウト機能を提供する。
- <xref:System.Windows.Forms.Control.ForeColor%2A>、<xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.Height%2A>、<xref:System.Windows.Forms.Control.Width%2A> など、ビジュアル表示に固有の多くのプロパティを含む。
- Windows フォーム コントロールが Microsoft® ActiveX® コントロールとして機能するために必要なセキュリティとスレッドのサポートを提供する。

インフラストラクチャの大部分は基底クラスによって提供されるため、独自の Windows フォーム コントロールを比較的簡単に開発できます。

## <a name="composite-controls"></a>複合コントロール

複合コントロールは、共通のコンテナーにカプセル化された Windows フォーム コントロールのコレクションです。 この種のコントロールは、*ユーザー コントロール* とも呼ばれます。 含まれているコントロールは、*内在コントロール* と呼ばれます。

複合コントロールは、含まれている各 Windows フォーム コントロールに関連する固有の機能をすべて保持し、それらのプロパティを選択的に公開してバインドできます。 また、開発者側での追加作業を必要としない多数の既定のキーボード処理機能も提供します。

たとえば、データベースの顧客の住所データを表示する複合コントロールを作成できます。 このコントロールには、データベース フィールドを表示するための <xref:System.Windows.Forms.DataGridView> コントロール、データ ソースへのバインドを処理するための <xref:System.Windows.Forms.BindingSource>、およびレコード間を移動するための <xref:System.Windows.Forms.BindingNavigator> コントロールが含まれます。 データ バインディング プロパティを選択的に公開したり、コントロール全体をパッケージ化してアプリケーション間で再利用したりできます。<!-- TODO For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).-->

複合コントロールを作成するには、<xref:System.Windows.Forms.UserControl> クラスから派生させます。 <xref:System.Windows.Forms.UserControl> 基底クラスは、子コントロールに対してキーボード ルーティングを提供し、複数の子コントロールを 1 つのグループとして機能させることができます。<!-- TODO For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).-->

## <a name="extended-controls"></a>拡張コントロール

既存の Windows フォーム コントロールから継承されたコントロールを派生できます。 この方法では、Windows フォーム コントロールの固有の機能をすべて保持し、カスタム プロパティ、メソッドなどの機能を追加してその機能を拡張できます。 この方法を使用して、基本コントロールの描画ロジックをオーバーライドし、そのユーザー インターフェイスの外観を変更して拡張できます。

たとえば、ユーザーがクリックした回数を追跡する、<xref:System.Windows.Forms.Button> コントロールから派生したコントロールを作成できます。

一部のコントロールでは、基底クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドすることで、コントロールのグラフィカル ユーザー インターフェイスにカスタムの外観を追加することもできます。 クリックを追跡する拡張ボタンの場合は、<xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドして <xref:System.Windows.Forms.Control.OnPaint%2A> の基本実装を呼び出し、<xref:System.Windows.Forms.Button> コントロールのクライアント領域の 1 つの隅にクリック数を描画します。

## <a name="custom-controls"></a>カスタム コントロール

コントロールを作成する別の方法は、<xref:System.Windows.Forms.Control> から継承することで、実質的に一から作成する方法です。 <xref:System.Windows.Forms.Control> クラスは、コントロールで必要とされるすべての基本的な機能 (マウスやキーボードの処理イベントなど) を提供しますが、コントロール固有の機能やグラフィカル インターフェイスは提供しません。

<xref:System.Windows.Forms.Control> クラスから継承することでコントロールを作成する場合は、<xref:System.Windows.Forms.UserControl> や既存の Windows フォーム コントロールから継承する場合よりも、はるかに多くの配慮と労力が必要です。 多くの実装が開発者に委ねられるため、作成されるコントロールは、複合コントロールや拡張コントロールよりも柔軟性に優れ、ニーズに合わせてコントロールを調整できます。

カスタム コントロールを実装するには、コントロールの <xref:System.Windows.Forms.Control.OnPaint%2A> イベントのコードと、必要な機能固有のコードを作成する必要があります。 また、<xref:System.Windows.Forms.Control.WndProc%2A> メソッドをオーバーライドして、Windows メッセージを直接処理することもできます。 これはコントロールを作成する最も強力な方法ですが、この手法を効果的に使用するには、Microsoft Win32® API を十分に理解している必要があります。

カスタム コントロールの例として、アナログ時計の外観と動作を複製した時計コントロールがあります。 内部 <xref:System.Windows.Forms.Timer> コンポーネントからの <xref:System.Windows.Forms.Timer.Tick> イベントに応答してカスタム ペインティングが呼び出されて、時計の針が移動します。<!-- TODO For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).-->

## <a name="activex-controls"></a>ActiveX コントロール

Windows フォーム インストラクチャは、Windows フォーム コントロールをホストするために最適化されていますが、ActiveX コントロールを使用することもできます。 Visual Studio では、このタスクに対するサポートが用意されています。<!-- TODO For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).-->

## <a name="windowless-controls"></a>ウィンドウなしのコントロール

Microsoft Visual Basic® 6.0 と ActiveX テクノロジは、"*ウィンドウなし*" のコントロールをサポートします。 ウィンドウなしのコントロールは、Windows フォームではサポートされていません。

## <a name="custom-design-experience"></a>カスタム デザイン エクスペリエンス

カスタムのデザイン時エクスペリエンスを実装する必要がある場合は、独自のデザイナーを作成できます。 複合コントロールの場合は、<xref:System.Windows.Forms.Design.ParentControlDesigner> または <xref:System.Windows.Forms.Design.DocumentDesigner> クラスからカスタム デザイナー クラスを派生させます。 拡張およびカスタム コントロールの場合は、<xref:System.Windows.Forms.Design.ControlDesigner> クラスからカスタム デザイナー クラスを派生させます。

コントロールをデザイナーに関連付けるには、<xref:System.ComponentModel.DesignerAttribute> を使用します。

次の情報は最新ではありませんが、役に立ちます。

- [(Visual Studio 2013) デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).
- [(Visual Studio 2013) 方法: デザイン時機能を活用した Windows フォーム コントロールを作成する](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))

## <a name="see-also"></a>関連項目

- [コントロールの使用の概要 (Windows フォーム .NET)](overview.md)

<!-- TODO: link to the ..\custom-controls\ content 

- [Developing Custom Windows Forms Controls](developing-custom-windows-forms-controls.md)
- [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md)
- [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md)
-->
