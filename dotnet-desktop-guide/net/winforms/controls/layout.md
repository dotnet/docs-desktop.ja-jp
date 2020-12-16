---
title: コントロールのレイアウト オプション
description: .NET 用 Windows フォームのレイアウトと配置に影響を与えるコントロールのさまざまな設定について説明します。 レイアウトに影響を与えるさまざまな種類のコントロール コンテナーについて説明します。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- forms [Windows Forms], aligning controls
- Windows Forms, aligning controls
- controls [Windows Forms], positioning
- controls [Windows Forms], aligning
- TabControl control [Windows Forms], about TabControl control
- SplitContainer control [Windows Forms], about SplitContainer control
- Panel control [Windows Forms], about Panel control
- GroupBox control [Windows Forms], about GroupBox control
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.openlocfilehash: 542decdf2555dcc01ff544a370f59ac73269ab6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942207"
---
# <a name="position-and-layout-of-controls-windows-forms-net"></a>コントロールの位置とレイアウト (Windows フォーム .NET)

Windows フォームでのコントロールの配置は、コントロールだけでなく、コントロールの親によっても決定されます。 この記事では、コントロールによって提供されるさまざまな設定と、レイアウトに影響を与えるさまざまな種類の親コンテナーについて説明します。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="fixed-position-and-size"></a>固定位置とサイズ

親の上に表示されるコントロールの位置は、親サーフェイスの左上に対して相対的な <xref:System.Windows.Forms.Control.Location> プロパティの値によって決まります。 親の左上の位置座標は `(x0,y0)` です。 コントロールのサイズは、<xref:System.Windows.Forms.Control.Size> プロパティによって決定され、コントロールの幅と高さを表します。

:::image type="content" source="media/layout/location+container.png" alt-text="コンテナーに対して相対的なコントロールの位置":::

自動配置が適用される親にコントロールが追加されると、コントロールの位置とサイズが変更されます。 この場合、親の種類によっては、コントロールの位置とサイズを手動で調整できないことがあります。

<xref:System.Windows.Forms.Control.MaximumSize%2A> と <xref:System.Windows.Forms.Control.MinimumSize%2A> プロパティは、コントロールに使用できる最小および最大の領域を設定するのに役立ちます。

## <a name="automatic-placement-and-size"></a>自動配置とサイズ

コントロールは、自動的に親の内部に配置できます。 親コンテナーには、配置が強制されるものもあれば、配置を制御するコントロールの設定に従うものもあります。 コントロールには、親の内部での自動配置とサイズを補助する <xref:System.Windows.Forms.Control.Dock%2A> および <xref:System.Windows.Forms.Control.Anchor> という 2 つのプロパティがあります。

描画順序が自動配置に影響することがあります。 コントロールが描画される順序は、親の <xref:System.Windows.Forms.Control.Controls> コレクション内でのコントロールのインデックスによって決まります。 このインデックスは **:::no-loc text="Z-order":::** と呼ばれます。 各コントロールは、コレクションに表示されるのとは逆の順序で描画されます。 つまり、コレクションは、最初に入ったものが最後に描画され、最後に入ったものが最初に描画されるコレクションです。

<xref:System.Windows.Forms.Control.MinimumSize%2A> と <xref:System.Windows.Forms.Control.MaximumSize%2A> プロパティは、コントロールに使用できる最小および最大の領域を設定するのに役立ちます。

### <a name="dock"></a>ドッキング

`Dock` プロパティは、コントロールのどの境界線を親の対応する辺に合わせるか、および親の内部でコントロールのサイズをどのように変更するかを設定します。

:::image type="content" source="media/layout/dock-modes.png" alt-text="ドッキング設定があるボタンを含む Windows フォーム。":::

コントロールがドッキングされると、コンテナーによってコントロールの占有スペースの決定、サイズ変更、配置が行われます。 コントロールの幅と高さは、ドッキングのスタイルに基づいて引き続き維持されます。 たとえば、コントロールが上部にドッキングされた場合、コントロールの <xref:System.Windows.Forms.Control.Height> は維持されますが、<xref:System.Windows.Forms.Control.Width> は自動的に調整されます。 コントロールが左側にドッキングされた場合、コントロールの <xref:System.Windows.Forms.Control.Width> は維持されますが、<xref:System.Windows.Forms.Control.Height> は自動的に調整されます。

コントロールをドッキングすると、その位置は自動的に制御されるため、コントロールの <xref:System.Windows.Forms.Control.Location> を手動で設定することはできません。

コントロールの **:::no-loc text="Z-order":::** は、ドッキングに影響します。 ドッキングされたコントロールがレイアウトされるとき、それらのために使用可能な領域が使用されます。 たとえば、最初にコントロールが描画され、上部にドッキングされた場合、コンテナーの幅全体を占有します。 次のコントロールが左側にドッキングされた場合は、使用可能な垂直方向の領域が小さくなります。

:::image type="content" source="media/layout/dock-top-then-left.png" alt-text="左側と上部にボタンがドッキングされ、上部の方が大きい Windows フォーム。":::

コントロールの **:::no-loc text="Z-order":::** が反転された場合は、左側にドッキングされたコントロールに使用可能な初期領域が多くなります。 コントロールにコンテナーの高さ全体が使用されます。 上部にドッキングされたコントロールは、使用可能な水平方向の領域が小さくなります。

:::image type="content" source="media/layout/dock-left-then-top.png" alt-text="左側と上部にボタンがドッキングされ、左側の方が大きい Windows フォーム。":::

コンテナーのサイズを拡大したり縮小したりすると、コンテナーにドッキングされているコントロールの位置とサイズが変更され、適用可能な位置とサイズが維持されます。

:::image type="content" source="media/layout/dock-resize.gif" alt-text="すべての位置にボタンがドッキングされた Windows フォームがどのようにサイズ変更されるかを示すアニメーション。":::

複数のコントロールがコンテナーの同じ側にドッキングされた場合、それらは **:::no-loc text="Z-order":::** に従って積み重ねられます。

:::image type="content" source="media/layout/dock-left-left.png" alt-text="2 つのボタンが左側にドッキングされた Windows フォーム。":::

### <a name="anchor"></a>アンカー

コントロールを固定すると、親コンテナーの 1 つ以上の辺にコントロールを結合できます。 コンテナーのサイズが変更されると、子コントロールは固定された側への距離を維持します。

コントロールは、制限なく 1 つ以上の辺に固定できます。 アンカーは、<xref:System.Windows.Forms.Control.Anchor> プロパティで設定されます。

:::image type="content" source="media/layout/anchor-resize.gif" alt-text="すべての位置にボタンが固定された Windows フォームがどのようにサイズ変更されるかを示すアニメーション。":::

### <a name="automatic-sizing"></a>サイズの自動調整

<xref:System.Windows.Forms.Control.AutoSize> プロパティを使用すると、必要に応じて、<xref:System.Windows.Forms.Control.PreferredSize> プロパティによって指定されたサイズに合わせてコントロールのサイズを変更できます。 特定のコントロールのサイズ変更動作を調整するには、`AutoSizeMode` プロパティを設定します。

<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティに対応しているコントロールは一部だけです。 また、<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティに対応している一部のコントロールは、`AutoSizeMode` プロパティにも対応しています。

| 動作は常にこうなります | 説明 |
|--|--|
| サイズの自動調整は、実行時の機能です。 | これは、コントロールが拡大または縮小されることはなく、それ以上の効果がないことを意味します。 |
| コントロールのサイズが変更された場合、その <xref:System.Windows.Forms.Control.Location%2A> プロパティの値は常に一定です。 | コントロールの内容が大きくなると、コントロールは右および下方向に拡大されます。 コントロールが左に拡大されることはありません。 |
| <xref:System.Windows.Forms.Control.AutoSize%2A> が `true` のとき、<xref:System.Windows.Forms.Control.Dock%2A> および <xref:System.Windows.Forms.Control.Anchor%2A> プロパティが適用されます。 | コントロールの <xref:System.Windows.Forms.Control.Location%2A> プロパティの値は、正しい値に調整されます。<br /><br /> <xref:System.Windows.Forms.Label> コントロールはこの規則の例外です。 ドッキングされた <xref:System.Windows.Forms.Label> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を `true` に設定すると、<xref:System.Windows.Forms.Label> コントロールは伸縮しません。 |
| コントロールの <xref:System.Windows.Forms.Control.MaximumSize%2A> および <xref:System.Windows.Forms.Control.MinimumSize%2A> プロパティは、<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値に関係なく、常に適用されます。 | <xref:System.Windows.Forms.Control.MaximumSize%2A> および <xref:System.Windows.Forms.Control.MinimumSize%2A> プロパティは、<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの影響を受けません。 |
| 既定では、最小サイズは設定されていません。 | つまり、コントロールが <xref:System.Windows.Forms.Control.AutoSize%2A> に従って縮小するように設定されていて、内容がない場合、その <xref:System.Windows.Forms.Control.Size%2A> プロパティの値は `(0x,0y)` です。 この場合、コントロールは縮小されて 1 つのポイントになり、容易に目につかなくなります。 |
| コントロールに <xref:System.Windows.Forms.Control.GetPreferredSize%2A> メソッドが実装されていない場合、<xref:System.Windows.Forms.Control.GetPreferredSize%2A> メソッドからは <xref:System.Windows.Forms.Control.Size%2A> プロパティに割り当てられた最後の値が返されます。 | これは、<xref:System.Windows.Forms.Control.AutoSize%2A> を `true` に設定しても効果がないことを意味します。 |
| <xref:System.Windows.Forms.TableLayoutPanel> セル内のコントロールは常に、<xref:System.Windows.Forms.Control.MinimumSize%2A> に達するまでセルに合わせて縮小されます。 | このサイズは、最大サイズとして適用されます。 これは、セルが <xref:System.Windows.Forms.SizeType.AutoSize> の行または列の一部である場合には当てはまりません。 |

## <a name="container-form"></a>コンテナー: フォーム

<xref:System.Windows.Forms.Form> は Windows フォームの主要なオブジェクトです。 通常、Windows フォーム アプリケーションのフォームは常に表示されます。 フォームにはコントロールが含まれており、コントロールの手動配置のための <xref:System.Windows.Forms.Control.Location> および <xref:System.Windows.Forms.Control.Size> プロパティが適用されます。 フォームは、自動配置のための [Dock](#dock) プロパティにも対応します。

ほとんどの場合、フォームの端にはグリップがあり、ユーザーがフォームのサイズを変更できるようになっています。 コントロールの <xref:System.Windows.Forms.Control.Anchor> プロパティを使用すると、フォームのサイズが変更されたときにコントロールのサイズを拡大したり縮小したりできます。

## <a name="container-panel"></a>コンテナー: パネル

<xref:System.Windows.Forms.Panel> コントロールは、コントロールをまとめてグループ化するという点でフォームに似ています。 フォームと同じように手動および自動の配置スタイルに対応しています。 詳細については、「[コンテナー: フォーム](#container-form)」セクションを参照してください。

パネルは、親とシームレスにブレンドされます。パネルの境界外にあるコントロールの領域は切り取られます。 コントロールがパネルの境界の外側にあり、<xref:System.Windows.Forms.Form.AutoScroll> が `true` に設定されている場合は、スクロール バーが表示され、ユーザーはパネルをスクロールできます。

[グループ ボックス](#container-group-box) コントロールとは異なり、パネルにはキャプションと境界線はありません。

:::image type="content" source="media/layout/panel-groupbox.png" alt-text="パネルとグループ ボックスを含む Windows フォーム。":::

上の図にあるパネルには、パネルの境界を示すために <xref:System.Windows.Forms.Panel.BorderStyle%2A> プロパティが設定されています。

## <a name="container-group-box"></a>コンテナー: グループ ボックス

<xref:System.Windows.Forms.GroupBox> コントロールは、他のコントロールの識別可能なグループ分けを提供します。 通常、グループ ボックスは、フォームを機能ごとに分割するために使用します。 たとえば、個人情報を表すフォームがあり、住所に関連するフィールドがグループ化されているとします。 デザイン時には、グループ ボックスを、それに含まれているコントロールと共に簡単に移動できます。

グループ ボックスは、フォームと同じように手動および自動の配置スタイルに対応しています。 詳細については、「[コンテナー: フォーム](#container-form)」セクションを参照してください。 グループ ボックスの場合も、パネルの境界外にあるコントロールの部分は切り取られます。

[パネル](#container-panel) コントロールとは異なり、グループ ボックスには、内容をスクロールしたり、スクロール バーを表示したりする機能はありません。

:::image type="content" source="media/layout/panel-groupbox.png" alt-text="パネルとグループ ボックスを含む Windows フォーム。":::

## <a name="container-flow-layout"></a>コンテナー: フロー レイアウト

<xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、水平または垂直のフローの方向に内容を整列させます。 コントロールの内容をある行から次の行、またはある列から次の列にラップすることができます。 また、内容をラップする代わりにクリップすることができます。  
  
<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> プロパティの値を設定して、フローの方向を指定できます。 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、右から左 (RTL) のレイアウトでフローの方向を正しく反転します。 また、<xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> プロパティの値を設定して、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの内容がラップまたはクリップされるかを指定することもできます。  

<xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティを `true` に設定すると、自動的に内容に合わせたサイズにします。 また、`FlowBreak` プロパティを子コントロールに提供します。 `FlowBreak` プロパティの値を `true` に設定することで、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールを現在のフロー方向のコントロールにレイアウトすること、および次の行または列にラップすることを停止します。  

:::image type="content" source="media/layout/flow.png" alt-text="2 つのフロー パネル コントロールを含む Windows フォーム。":::

上の図にある 2 つの `FlowLayoutPanel` コントロールには、コントロールの境界を示すために <xref:System.Windows.Forms.Panel.BorderStyle> プロパティが設定されています。

## <a name="container-table-layout"></a>コンテナー: テーブル レイアウト

<xref:System.Windows.Forms.TableLayoutPanel> コントロールは、その内容をグリッド内に配置します。 レイアウトはデザイン時と実行時の両方で行われるため、アプリケーション環境の変更に合わせて動的に変更できます。 これにより、パネル内のコントロールを適切にサイズ変更することができるため、親コントロールのサイズ変更や、ローカライズによるテキスト長の変更などの変更に対応できます。

Windows フォーム コントロールは、<xref:System.Windows.Forms.TableLayoutPanel> の他のインスタンスを含めて、<xref:System.Windows.Forms.TableLayoutPanel> コントロールの子にすることができます。 これにより、実行時の変化に適応する高度なレイアウトを構築することができます。

<xref:System.Windows.Forms.TableLayoutPanel> コントロールが完全に子コントロールになった後で、(水平または垂直の) 展開の方向を制御することもできます。 既定では、<xref:System.Windows.Forms.TableLayoutPanel> コントロールは行を追加することで下方向に拡張します。

<xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> および <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> プロパティを使用して、行と列のサイズとスタイルを制御できます。 行または列のプロパティを個別に設定することができます。

<xref:System.Windows.Forms.TableLayoutPanel> コントロールは、その子コントロールに `Cell`、`Column`、`Row`、`ColumnSpan`、および `RowSpan` の各プロパティを追加します。

:::image type="content" source="media/layout/table.png" alt-text="テーブル レイアウト コントロールを含む Windows フォーム。":::

上の図にあるテーブルには、各セルの境界を示すために <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle> プロパティが設定されています。

## <a name="container-split-container"></a>コンテナー: 分割コンテナー

Windows フォームの <xref:System.Windows.Forms.SplitContainer> コントロールは複合コントロールと考えることができ、移動可能なバーで区切られた 2 つのパネルです。 マウス ポインターがバーの上に移動すると、ポインターの形が変わり、バーが移動可能であることを示します。  

<xref:System.Windows.Forms.SplitContainer> コントロールを使用すると複雑なユーザー インターフェイスを作成できます。多くの場合、1 つのパネルでの選択項目によって、別のパネルに表示されるオブジェクトが決定します。 この配置は、情報の表示と参照に対して効果的です。 2 つのパネルを使用することで、情報を領域に集約でき、バーまたは "スプリッター" により、ユーザーがパネルを簡単にサイズ変更できます。

:::image type="content" source="media/layout/splitcontainer.png" alt-text="入れ子になった分割コンテナーを含む Windows フォーム。":::

上の図では、分割コンテナーによってペインが左右に作成されています。 右側のペインには、<xref:System.Windows.Forms.SplitContainer.Orientation> が <xref:System.Windows.Forms.Orientation.Vertical> に設定された 2 番目の分割コンテナーが含まれています。 <xref:System.Windows.Forms.SplitContainer.BorderStyle> プロパティは、各パネルの境界を示すように設定されています。

## <a name="container-tab-control"></a>コンテナー: タブ コントロール

<xref:System.Windows.Forms.TabControl> は、ノートの仕切りや書類キャビネットのフォルダー セットのラベルに似た、複数のタブを表示します。 タブには画像やその他のコントロールを含めることができます。 タブ コントロールは、コントロール パネルや表示プロパティなど、Windows オペレーティング システムのさまざまな場所に表示される複数ページのダイアログ ボックスの種類を生成するために使用します。 さらに、<xref:System.Windows.Forms.TabControl> を使用して、関連するプロパティのグループを設定するために使用されるプロパティ ページを作成することもできます。

<xref:System.Windows.Forms.TabControl> の最も重要なプロパティは、個々のタブを含む <xref:System.Windows.Forms.TabControl.TabPages%2A> です。 個々のタブは <xref:System.Windows.Forms.TabPage> オブジェクトです。

:::image type="content" source="media/layout/tabcontrol.png" alt-text="2 つのタブ ページがあるタブ コントロールを含む Windows フォーム。":::
