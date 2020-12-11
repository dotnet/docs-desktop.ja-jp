---
title: ToolStrip コントロールのアーキテクチャ
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983872"
---
# <a name="toolstrip-control-architecture"></a>ToolStrip コントロールのアーキテクチャ

<xref:System.Windows.Forms.ToolStrip>クラスと <xref:System.Windows.Forms.ToolStripItem> クラスは、ツールバー、状態、およびメニュー項目を表示するための柔軟で拡張可能なシステムを提供します。 これらのクラスはすべて、名前空間に含まれ <xref:System.Windows.Forms> ており、通常は "ToolStrip" プレフィックス (など <xref:System.Windows.Forms.ToolStripOverflow> ) または "ストリップ" サフィックス (など) を使用して名前が付けられ <xref:System.Windows.Forms.MenuStrip> ます。

## <a name="toolstrip"></a>ToolStrip

次のトピックでは、 <xref:System.Windows.Forms.ToolStrip> とそれから派生するコントロールについて説明します。

<xref:System.Windows.Forms.ToolStrip> は、、、およびの抽象基本クラスです <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ContextMenuStrip> 。 次のオブジェクトモデルは、 <xref:System.Windows.Forms.ToolStrip> 継承階層を示しています。

![ToolStrip オブジェクトモデルを示す図。](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

内のすべての項目にアクセスするには、 <xref:System.Windows.Forms.ToolStrip> コレクションを使用 <xref:System.Windows.Forms.ToolStrip.Items%2A> します。 内のすべての項目にアクセスするには、 <xref:System.Windows.Forms.ToolStripDropDownItem> コレクションを使用 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> します。 から派生したクラスでは、プロパティを使用して、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> 現在表示されている項目のみにアクセスすることもできます。 これらの項目は、現在オーバーフローメニューに含まれていません。

次の項目は、すべての方向にとの両方でシームレスに動作するように設計されてい <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ます。 これらは、デザイン時にコントロールに対して既定で使用でき <xref:System.Windows.Forms.ToolStrip> ます。

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip> は、を置き換えるトップレベルのコンテナーです <xref:System.Windows.Forms.MainMenu> 。 また、主要な処理とマルチドキュメントインターフェイス (MDI) 機能も用意されています。 機能的には、 <xref:System.Windows.Forms.ToolStripDropDownItem> と <xref:System.Windows.Forms.ToolStripMenuItem> 共に動作し <xref:System.Windows.Forms.MenuStrip> ますが、から派生 <xref:System.Windows.Forms.ToolStripItem> します。

次の項目は、すべての方向にとの両方でシームレスに動作するように設計されてい <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ます。 これらは、デザイン時にコントロールに対して既定で使用でき <xref:System.Windows.Forms.MenuStrip> ます。

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip> コントロールを置き換え <xref:System.Windows.Forms.StatusBar> ます。 の特別な機能としては、 <xref:System.Windows.Forms.StatusStrip> カスタムテーブルレイアウト、フォームのサイズ変更と移動グリップのサポート、プロパティがあり `Spring` ます。これにより、は、 <xref:System.Windows.Forms.ToolStripStatusLabel> 使用可能な領域を自動的に埋めることができます。

次の項目は、すべての方向にとの両方でシームレスに動作するように設計されてい <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ます。 これらは、デザイン時にコントロールに対して既定で使用でき <xref:System.Windows.Forms.StatusStrip> ます。

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenu> が <xref:System.Windows.Forms.ContextMenuStrip> に置き換えられます。 を任意のコントロールに関連付けることができ <xref:System.Windows.Forms.ContextMenuStrip> 、右クリックするとコンテキストメニュー (またはショートカットメニュー) が自動的に表示されます。 メソッドを使用し <xref:System.Windows.Forms.ContextMenuStrip> て、をプログラムで表示でき <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> ます。 <xref:System.Windows.Forms.ContextMenuStrip> 動的な <xref:System.Windows.Forms.ToolStripDropDown.Opening> <xref:System.Windows.Forms.ToolStripDropDown.Closing> 作成や複数クリックのシナリオを処理するためのキャンセル可能なイベントとイベントをサポートします。 <xref:System.Windows.Forms.ContextMenuStrip> イメージ、メニュー項目のチェック状態、テキスト、アクセスキー、ショートカット、およびカスケードメニューをサポートします。

次の項目は、すべての方向にとの両方でシームレスに動作するように設計されてい <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ます。 これらは、デザイン時にコントロールに対して既定で使用でき <xref:System.Windows.Forms.ContextMenuStrip> ます。

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>ToolStrip 汎用機能

次のトピックでは、およびの派生コントロールに共通する機能と動作について説明し <xref:System.Windows.Forms.ToolStrip> ます。

#### <a name="painting"></a>画

コントロールでは、 <xref:System.Windows.Forms.ToolStrip> いくつかの方法でカスタムの描画を行うことができます。 他の Windows フォームコントロールと同様に、との両方に、 <xref:System.Windows.Forms.ToolStrip> オーバーライド可能 <xref:System.Windows.Forms.ToolStripItem> な `OnPaint` メソッドとイベントがあり `Paint` ます。 通常の描画と同様に、座標系はコントロールのクライアント領域を基準としています。つまり、コントロールの左上隅は0、0です。 の `Paint` イベントと `OnPaint` メソッドは、 <xref:System.Windows.Forms.ToolStripItem> 他のコントロール描画イベントと同様に動作します。

また、コントロールは、 <xref:System.Windows.Forms.ToolStrip> クラスを介した項目およびコンテナーのレンダリングにより詳細にアクセスできるようにし <xref:System.Windows.Forms.ToolStripRenderer> ます。これには、背景、項目の背景、項目の画像、項目の矢印、項目のテキスト、およびの境界線を描画するためのオーバーライド可能なメソッドがあり <xref:System.Windows.Forms.ToolStrip> ます。 これらのメソッドのイベント引数は、四角形、色、テキスト形式など、必要に応じて調整できるいくつかのプロパティを公開します。

項目を描画する方法のいくつかの側面だけを調整するには、通常、をオーバーライドし <xref:System.Windows.Forms.ToolStripRenderer> ます。

新しい項目を作成しているときに、描画のすべての側面を制御する場合は、メソッドをオーバーライドし `OnPaint` ます。 内から、 `OnPaint` のメソッドを使用でき <xref:System.Windows.Forms.ToolStripRenderer> ます。

既定では、は、設定を利用して、 <xref:System.Windows.Forms.ToolStrip> ダブルバッファリングされ <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> ます。

#### <a name="parenting"></a>親子

コンテナーの所有権と親の概念は、 <xref:System.Windows.Forms.ToolStrip> 他の Windows フォームコンテナーコントロールよりもコントロールが複雑になります。 これは、オーバーフローなどの動的なシナリオをサポートし、複数の項目にわたるドロップダウン項目を共有 <xref:System.Windows.Forms.ToolStrip> し、コントロールからの生成をサポートするために必要です <xref:System.Windows.Forms.ContextMenuStrip> 。

次の一覧では、親子関係に関連するメンバーとその使用方法について説明します。

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> ドロップダウン項目のソースである項目にアクセスします。 これはに似 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> ていますが、コントロールを返すのではなく、を返し <xref:System.Windows.Forms.ToolStripItem> ます。

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A><xref:System.Windows.Forms.ContextMenuStrip>複数のコントロールが同じを共有する場合に、のソースとなるコントロールを決定します <xref:System.Windows.Forms.ContextMenuStrip> 。

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> は、プロパティに対する読み取り専用のアクセサーです <xref:System.Windows.Forms.ToolStripItem.Parent%2A> 。 親は、項目が表示されている現在のが返された現在のが <xref:System.Windows.Forms.ToolStrip> オーバーフロー領域に存在する可能性があるという点で、所有者と異なります。

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A><xref:System.Windows.Forms.ToolStrip>項目コレクションに現在のが含まれているを返し <xref:System.Windows.Forms.ToolStripItem> ます。 これは、 <xref:System.Windows.Forms.ToolStrip.ImageList%2A> <xref:System.Windows.Forms.ToolStrip> オーバーフローを処理する特殊なコードを記述しなくても、トップレベルのプロパティを参照するための最適な方法です。

#### <a name="behavior-of-inherited-controls"></a>継承されたコントロールの動作

次のコントロールは、継承で使用されるたびにロックされます。

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel> これには、のパネルと、個別のコントロールが含まれ <xref:System.Windows.Forms.ToolStripContainer> <xref:System.Windows.Forms.ToolStripPanel> ます。

たとえば、前の一覧の1つまたは複数のコントロールを使用して、新しい Windows フォームアプリケーションを作成します。 1つまたは複数のコントロールのアクセス修飾子を `public` またはに設定し、プロジェクトをビルドし `protected` ます。 最初のフォームから継承したフォームを追加し、継承されたコントロールを選択します。 コントロールがロックされ、アクセス修飾子がのように動作し `private` ます。

#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer の継承のサポート

コントロールは、 <xref:System.Windows.Forms.ToolStripContainer> 次の例のように、制限付きの継承されたシナリオをサポートします。

1. 新しい Windows フォーム アプリケーションを作成します。

2. フォームに <xref:System.Windows.Forms.ToolStripContainer> を追加します。

3. のアクセス修飾子 <xref:System.Windows.Forms.ToolStripContainer> をまたはに設定し `public` `protected` ます。

4. 、、およびの各コントロールの任意の組み合わせ <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> をの領域に追加し <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripContainer> ます。

5. プロジェクトをビルドします。

6. 最初のフォームから継承するフォームを追加します。

7. フォームで継承されたを選択し <xref:System.Windows.Forms.ToolStripContainer> ます。

#### <a name="inherited-behavior-of-child-controls"></a>子コントロールの継承された動作

前の手順を完了すると、次の継承された動作が行われます。

- デザイナーでは、コントロールが継承されたアイコンと共に表示されます。

- コントロールはロックされています。 <xref:System.Windows.Forms.ToolStripPanel> コンテンツを選択または再配置することはできません。

- にコントロールを追加したり、 <xref:System.Windows.Forms.ToolStripContentPanel> コントロールを移動したり、の子コントロールを作成したりすることができ <xref:System.Windows.Forms.ToolStripContentPanel> ます。

- フォームをビルドした後も変更は保持されます。

  > [!NOTE]
  > に含まれるすべてのコントロールからアクセス修飾子を削除 <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripContainer> します。 のアクセス修飾子は、 <xref:System.Windows.Forms.ToolStripContainer> コントロール全体を制御します。

#### <a name="partial-trust"></a>部分信頼

部分信頼におけるの制限は、承認されていない `ToolStrip` 人物やサービスによって使用される個人情報が誤って入力されないように設計されています。 保護対策は次のとおりです。

- `ToolStripDropDown` コントロール <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> では、に項目を表示する必要があり <xref:System.Windows.Forms.ToolStripControlHost> ます。 これは、、、などの組み込みコントロールと、 <xref:System.Windows.Forms.ToolStripTextBox> ユーザーが作成したコントロールの両方に適用さ <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ToolStripProgressBar> れます。 この要件が満たされていない場合、これらの項目は表示されません。 例外をスローすることはありません。

- <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A>プロパティをに設定 `false` することはできません。また、キャンセル可能 <xref:System.Windows.Forms.ToolStripDropDown.Closing> なイベントパラメーターは無視されます。 これにより、ドロップダウン項目を終了せずに複数のキーストロークを入力することはできません。 この要件が満たされていない場合、このような項目は表示されません。 例外をスローすることはありません。

- 以外の部分信頼コンテキストで発生した場合、多くのキーストローク処理イベントは発生しません <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 。

- <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>が付与されていない場合、アクセスキーは処理されません。

#### <a name="usage"></a>使用方法

次の使用パターンは、 <xref:System.Windows.Forms.ToolStrip> レイアウト、キーボード操作、およびエンドユーザーの動作に影響します。

- に参加 <xref:System.Windows.Forms.ToolStripPanel>

  は、 <xref:System.Windows.Forms.ToolStrip> との間で再配置でき <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripPanel> ます。 `Dock`プロパティは無視され、プロパティがの場合は、 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> `false` 項目がに追加されたときにのサイズが <xref:System.Windows.Forms.ToolStrip> 大きく <xref:System.Windows.Forms.ToolStripPanel> なります。 通常、は <xref:System.Windows.Forms.ToolStrip> タブオーダーには参加しません。

- ドッキング

  は、固定された位置にある <xref:System.Windows.Forms.ToolStrip> コンテナーの1つの側に配置され、そのサイズはドッキングされるエッジ全体で拡大されます。 通常、は <xref:System.Windows.Forms.ToolStrip> タブオーダーには参加しません。

- 絶対配置

  は <xref:System.Windows.Forms.ToolStrip> 他のコントロールと同じように、プロパティによって配置され、 <xref:System.Windows.Forms.Control.Location%2A> 固定サイズであり、通常はタブオーダーに含まれます。

#### <a name="keyboard-interaction"></a>キーボード操作

##### <a name="access-keys"></a>アクセスキー

ALT キーと組み合わせて、またはその後、アクセスキーは、キーボードを使用してコントロールをアクティブ化するための1つの方法です。 <xref:System.Windows.Forms.ToolStrip> 明示的および暗黙的なアクセスキーの両方をサポートします。 明示的な定義では、文字の前にアンパサンド (&) 文字を使用します。 暗黙の定義では、特定のプロパティの文字の順序に基づいて一致する項目の検索を試みるアルゴリズムが使用さ `Text` れます。

##### <a name="shortcut-keys"></a>ショートカット キー

によって使用されるショートカットキーでは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.Keys> (順序固有ではない) 列挙型の組み合わせを使用して、ショートカットキーを定義します。 また、プロパティを使用して、 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> ショートカットキーをテキストのみで表示することもできます。たとえば、"delete" の代わりに "del" を表示することもできます。

##### <a name="navigation"></a>ナビゲーション

ALT キーは、が <xref:System.Windows.Forms.MenuStrip> 指すをアクティブにし <xref:System.Windows.Forms.Form.MainMenuStrip%2A> ます。 そこから、CTRL キーを押しながら TAB キーを押すと、内のコントロール間を移動 <xref:System.Windows.Forms.ToolStrip> `ToolStripPanel` できます。 テンキーの TAB キーと方向キーは、内の項目間を移動し <xref:System.Windows.Forms.ToolStrip> ます。 特殊なアルゴリズムは、オーバーフロー領域でのナビゲーションを処理します。 SPACE キーを押すと、、、またはが選択さ <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolStripDropDownButton> <xref:System.Windows.Forms.ToolStripSplitButton> れます。

##### <a name="focus-and-validation"></a>フォーカスと検証

ALT キーでアクティブにした場合、 <xref:System.Windows.Forms.MenuStrip> またはは <xref:System.Windows.Forms.ToolStrip> 通常、フォーカスを持つコントロールからフォーカスを取得したり削除したりすることはありません。 のまたはドロップダウン内でホストされているコントロールがある場合、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip> ユーザーが TAB キーを押したときにコントロールのフォーカスが得られます。 一般に、 <xref:System.Windows.Forms.Control.GotFocus> の、 <xref:System.Windows.Forms.Control.LostFocus> 、 <xref:System.Windows.Forms.Control.Enter> 、 <xref:System.Windows.Forms.Control.Leave> の各イベントは、 <xref:System.Windows.Forms.MenuStrip> キーボードによってアクティブ化されるときに発生しない可能性があります。 このような場合は、 <xref:System.Windows.Forms.MenuStrip.MenuActivate> イベントとイベントを代わりに使用 <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> します。

既定では、<xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> は `false` です。 <xref:System.Windows.Forms.ContainerControl.Validate%2A>検証を実行するには、フォームで明示的にを呼び出します。

#### <a name="layout"></a>Layout

プロパティを <xref:System.Windows.Forms.ToolStrip> 使用してのメンバーの1つを選択することによって、レイアウトを制御し <xref:System.Windows.Forms.ToolStripLayoutStyle> <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> ます。

##### <a name="stack-layouts"></a>スタックレイアウト

スタックとは、の両端にある項目の横に配置することです <xref:System.Windows.Forms.ToolStrip> 。 次の一覧では、スタックレイアウトについて説明します。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow> は既定値です。 この設定により、は、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Orientation%2A> ドラッグアンドドッキングのシナリオを処理するために、プロパティに従って自動的にレイアウトを変更します。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> 項目を <xref:System.Windows.Forms.ToolStrip> 縦に並べて表示します。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> 項目を <xref:System.Windows.Forms.ToolStrip> 水平方向に横に並べて表示します。

##### <a name="other-features-of-stack-layouts"></a>スタックレイアウトのその他の機能

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 項目の位置を示すの末尾を決定 <xref:System.Windows.Forms.ToolStrip> します。

項目が内に収まらない場合は、 <xref:System.Windows.Forms.ToolStrip> オーバーフローボタンが自動的に表示されます。 プロパティの設定は、 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 項目が常にオーバーフロー領域に表示されるか、必要に応じて表示されるか、または行わないかを決定します。

イベントでは、プロパティを調べて、 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 項目が <xref:System.Windows.Forms.ToolStripItem.Placement%2A> メインに配置されたか、 <xref:System.Windows.Forms.ToolStrip> オーバーフローしたか、または項目が現在まったく表示されていないかどうかを確認でき <xref:System.Windows.Forms.ToolStrip> ます。 項目が表示されない一般的な理由として、項目がメインに合わなかったこと <xref:System.Windows.Forms.ToolStrip> と、その <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> プロパティがに設定されていることが挙げられ <xref:System.Windows.Forms.ToolStripItemOverflow.Never> ます。

に移動 <xref:System.Windows.Forms.ToolStrip> し、をに設定して、移動可能にし <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> <xref:System.Windows.Forms.ToolStripGripStyle.Visible> ます。

##### <a name="other-layout-options"></a>その他のレイアウトオプション

その他のレイアウトオプションは、 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> と <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> です。

##### <a name="flow-layout"></a>フロー レイアウト

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> レイアウトは、、、およびの既定の設定です <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripDropDownMenu> <xref:System.Windows.Forms.ToolStripOverflow> 。 これはに似てい <xref:System.Windows.Forms.FlowLayoutPanel> ます。 レイアウトの機能 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> は次のとおりです。

- のすべての機能 <xref:System.Windows.Forms.FlowLayoutPanel> は、プロパティによって公開され <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> ます。 クラスをクラスにキャストする必要があり <xref:System.Windows.Forms.LayoutSettings> <xref:System.Windows.Forms.FlowLayoutSettings> ます。

- コードでプロパティとプロパティを使用して、行内の項目を揃えることができ <xref:System.Windows.Forms.ToolStripItem.Dock%2A> <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> ます。

- <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> プロパティは無視されます。

- イベントでは、プロパティを調べて、 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 項目がメインに配置されたか、 <xref:System.Windows.Forms.ToolStrip> または一致していないかを判断できます。

- グリップはレンダリングされないため、 <xref:System.Windows.Forms.ToolStrip> 内の <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> レイアウトスタイルのは <xref:System.Windows.Forms.ToolStripPanel> 移動できません。

- <xref:System.Windows.Forms.ToolStrip>オーバーフローボタンはレンダリングされず、 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> は無視されます。

##### <a name="table-layout"></a>テーブル レイアウト

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table> レイアウトがの既定値です <xref:System.Windows.Forms.StatusStrip> 。 これはに似てい <xref:System.Windows.Forms.TableLayoutPanel> ます。 レイアウトの機能 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> は次のとおりです。

- のすべての機能 <xref:System.Windows.Forms.TableLayoutPanel> は、プロパティによって公開され <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> ます。 クラスをクラスにキャストする必要があり <xref:System.Windows.Forms.LayoutSettings> <xref:System.Windows.Forms.TableLayoutSettings> ます。

- <xref:System.Windows.Forms.ToolStripItem.Dock%2A>コードでプロパティとプロパティを使用して、 <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> テーブルセル内のアイテムを配置できます。

- <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> プロパティは無視されます。

- イベントでは、プロパティを調べて、 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 項目がメインに配置されたか、 <xref:System.Windows.Forms.ToolStrip> または一致していないかを判断できます。

- グリップはレンダリングされないため、 <xref:System.Windows.Forms.ToolStrip> 内の <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> レイアウトスタイルのは <xref:System.Windows.Forms.ToolStripPanel> 移動できません。

- <xref:System.Windows.Forms.ToolStrip>オーバーフローボタンはレンダリングされず、 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> は無視されます。

## <a name="toolstripitem"></a>ToolStripItem

次のトピックでは、 <xref:System.Windows.Forms.ToolStripItem> とそれから派生するコントロールについて説明します。

<xref:System.Windows.Forms.ToolStripItem> は、に入るすべての項目の抽象基本クラスです <xref:System.Windows.Forms.ToolStrip> 。 次のオブジェクトモデルは、 <xref:System.Windows.Forms.ToolStripItem> 継承階層を示しています。

![ToolStripItem オブジェクトモデルを示す図。](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem> クラスは、から直接継承さ <xref:System.Windows.Forms.ToolStripItem> れるか、またはから間接的に継承さ <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStripControlHost> <xref:System.Windows.Forms.ToolStripDropDownItem> れます。

<xref:System.Windows.Forms.ToolStripItem> コントロールは、、、、またはに含まれている必要があり <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ContextMenuStrip> ます。フォームに直接追加することはできません。 さまざまなコンテナークラスは、コントロールの適切なサブセットを含むように設計されてい <xref:System.Windows.Forms.ToolStripItem> ます。

次の表に、ストック <xref:System.Windows.Forms.ToolStripItem> コントロールと、それらが最適なコンテナーを示します。 任意の <xref:System.Windows.Forms.ToolStrip> 項目を派生した任意のコンテナーでホストできますが <xref:System.Windows.Forms.ToolStrip> 、これらの項目は次のコンテナーで最適に表示されるように設計されています。

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown> デザイナーのツールボックスには表示されません。

|含まれている項目|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|
|<xref:System.Windows.Forms.ToolStripButton>|はい|いいえ|いいえ|いいえ|はい|
|<xref:System.Windows.Forms.ToolStripComboBox>|はい|はい|はい|いいえ|はい|
|<xref:System.Windows.Forms.ToolStripSplitButton>|はい|いいえ|いいえ|はい|はい|
|<xref:System.Windows.Forms.ToolStripLabel>|はい|いいえ|いいえ|はい|はい|
|<xref:System.Windows.Forms.ToolStripSeparator>|はい|はい|はい|いいえ|はい|
|<xref:System.Windows.Forms.ToolStripDropDownButton>|はい|いいえ|いいえ|はい|はい|
|<xref:System.Windows.Forms.ToolStripTextBox>|はい|はい|はい|いいえ|はい|
|<xref:System.Windows.Forms.ToolStripMenuItem>|いいえ|はい|はい|いいえ|いいえ|
|<xref:System.Windows.Forms.ToolStripStatusLabel>|いいえ|いいえ|いいえ|はい|いいえ|
|<xref:System.Windows.Forms.ToolStripProgressBar>|はい|いいえ|いいえ|はい|いいえ|
|<xref:System.Windows.Forms.ToolStripControlHost>|はい|はい|いいえ|はい|はい|

### <a name="toolstripbutton"></a>ToolStripButton

<xref:System.Windows.Forms.ToolStripButton> は、のボタン項目です <xref:System.Windows.Forms.ToolStrip> 。 さまざまな境界線スタイルを使用して表示することができ、それを使用して操作状態を表したり、アクティブ化したりすることができます。 既定でフォーカスを設定するように定義することもできます。

### <a name="toolstriplabel"></a>ToolStripLabel

は、 <xref:System.Windows.Forms.ToolStripLabel> コントロールにラベル機能を提供し <xref:System.Windows.Forms.ToolStrip> ます。 は <xref:System.Windows.Forms.ToolStripLabel> 、 <xref:System.Windows.Forms.ToolStripButton> 既定ではフォーカスが得られず、プッシュまたは強調表示されないに似ています。

<xref:System.Windows.Forms.ToolStripLabel> ホストされた項目として、アクセスキーをサポートします。

で、、、およびの各プロパティを使用して、の <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> <xref:System.Windows.Forms.ToolStripLabel> リンクコントロールをサポートし <xref:System.Windows.Forms.ToolStrip> ます。

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel> は、 <xref:System.Windows.Forms.ToolStripLabel> 専用に設計されたのバージョンです <xref:System.Windows.Forms.StatusStrip> 。 特別な機能には <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A> 、、、およびがあり <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A> <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> ます。

### <a name="toolstripseparator"></a>ToolStripSeparator

は、 <xref:System.Windows.Forms.ToolStripSeparator> 向きに応じて、ツールバーまたはメニューに垂直または水平の線を追加します。 メニュー上の項目など、項目のグループ化や区別を行います。

デザイン時にを追加するには、 <xref:System.Windows.Forms.ToolStripSeparator> ドロップダウンリストからを選択します。 ただし、 <xref:System.Windows.Forms.ToolStripSeparator> デザイナーテンプレートノードまたはメソッドのいずれかでハイフン (-) を入力して、を自動的に作成することもでき <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> ます。

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost> は、、、およびの抽象基本クラスです <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ToolStripTextBox> <xref:System.Windows.Forms.ToolStripProgressBar> 。 <xref:System.Windows.Forms.ToolStripControlHost> では、次の2つの方法で、カスタムコントロールを含む他のコントロールをホストできます。

- <xref:System.Windows.Forms.ToolStripControlHost>から派生したクラスを使用して、を構築 <xref:System.Windows.Forms.Control> します。 ホストされるコントロールとプロパティに完全にアクセスするには、 <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> そのプロパティを表す実際のクラスにキャストする必要があります。

- <xref:System.Windows.Forms.ToolStripControlHost>を拡張し、継承されたクラスのパラメーターなしのコンストラクターで、から派生したクラスを渡す基本クラスのコンストラクターを呼び出し <xref:System.Windows.Forms.Control> ます。 このオプションを使用すると、に簡単にアクセスできるように、一般的なコントロールメソッドとプロパティをラップでき <xref:System.Windows.Forms.ToolStrip> ます。

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox> は、 <xref:System.Windows.Forms.ComboBox> でホストするために最適化されたです <xref:System.Windows.Forms.ToolStrip> 。 ホストされるコントロールのプロパティとイベントのサブセットはレベルで公開され <xref:System.Windows.Forms.ToolStripComboBox> ますが、基になる <xref:System.Windows.Forms.ComboBox> コントロールにはプロパティを使用して完全にアクセスでき <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> ます。

### <a name="toolstriptextbox"></a>ToolStripTextBox

<xref:System.Windows.Forms.ToolStripTextBox> は、 <xref:System.Windows.Forms.TextBox> でホストするために最適化されたです <xref:System.Windows.Forms.ToolStrip> 。 ホストされるコントロールのプロパティとイベントのサブセットはレベルで公開され <xref:System.Windows.Forms.ToolStripTextBox> ますが、基になる <xref:System.Windows.Forms.TextBox> コントロールにはプロパティを使用して完全にアクセスでき <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> ます。

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar> は、 <xref:System.Windows.Forms.ProgressBar> でホストするために最適化されたです <xref:System.Windows.Forms.ToolStrip> 。 ホストされるコントロールのプロパティとイベントのサブセットはレベルで公開され <xref:System.Windows.Forms.ToolStripProgressBar> ますが、基になる <xref:System.Windows.Forms.ProgressBar> コントロールにはプロパティを使用して完全にアクセスでき <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> ます。

### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem

<xref:System.Windows.Forms.ToolStripDropDownItem> は、、、およびの抽象基本クラスであり、 <xref:System.Windows.Forms.ToolStripMenuItem> <xref:System.Windows.Forms.ToolStripDropDownButton> 項目を <xref:System.Windows.Forms.ToolStripSplitButton> 直接ホストすることも、ドロップダウンコンテナーで追加の項目をホストすることもできます。 これを行うには、 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> プロパティをに設定 <xref:System.Windows.Forms.ToolStripDropDown> し <xref:System.Windows.Forms.ToolStrip.Items%2A> 、のプロパティを設定し <xref:System.Windows.Forms.ToolStripDropDown> ます。 プロパティを使用して、これらのドロップダウン項目に直接アクセス <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> します。

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem> は、 <xref:System.Windows.Forms.ToolStripDropDownItem> およびで動作し、 <xref:System.Windows.Forms.ToolStripDropDownMenu> <xref:System.Windows.Forms.ContextMenuStrip> メニューの特別な強調表示、レイアウト、および列の配置を処理するです。

### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton

<xref:System.Windows.Forms.ToolStripDropDownButton> はのように見え <xref:System.Windows.Forms.ToolStripButton> ますが、ユーザーがクリックするとドロップダウン領域が表示されます。 プロパティを設定して、ドロップダウン矢印を表示または非表示にし <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> ます。 <xref:System.Windows.Forms.ToolStripDropDownButton> を <xref:System.Windows.Forms.ToolStripOverflowButton> オーバーフローする項目を表示するをホストし <xref:System.Windows.Forms.ToolStrip> ます。

### <a name="toolstripsplitbutton"></a>ToolStripSplitButton

<xref:System.Windows.Forms.ToolStripSplitButton> ボタンとドロップダウンボタンの機能を組み合わせます。

プロパティを使用して、選択した <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> <xref:System.Windows.Forms.Control.Click> ドロップダウン項目のイベントと、ボタンに表示されている項目を同期します。

### <a name="toolstripitem-generic-features"></a>ToolStripItem 汎用機能

<xref:System.Windows.Forms.ToolStripItem> には、コントロールを継承するための次の一般的な機能とオプションが用意されています。

- コアイベント

- イメージの処理

- Alignment

- テキストとイメージの関係

- 表示スタイル

#### <a name="core-events"></a>コアイベント

<xref:System.Windows.Forms.ToolStripItem> コントロールは、独自のクリック、マウス、および描画イベントを受け取り、一部のキーボード前処理も実行できます。

#### <a name="image-handling"></a>イメージの処理

<xref:System.Windows.Forms.ToolStripItem.Image%2A>、、 <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> 、 <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> 、およびの <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 各プロパティは、イメージ処理のさまざまな側面に関連します。 コントロール内のイメージを使用する <xref:System.Windows.Forms.ToolStrip> には、これらのプロパティを直接設定するか、実行時のみのプロパティを設定し <xref:System.Windows.Forms.ToolStrip.ImageList%2A> ます。

イメージのスケーリングは、次のように、との両方のプロパティの相互作用によって決定され <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripItem> ます。

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> は、イメージの <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 設定とコンテナーの設定の組み合わせによって決定される最終的なイメージの小数点以下桁数です <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 。

  - <xref:System.Windows.Forms.ToolStrip.AutoSize%2A>が `true` (既定値) であり <xref:System.Windows.Forms.ToolStripItemImageScaling> 、がである場合 <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit> 、イメージのスケーリングは行われず、 <xref:System.Windows.Forms.ToolStrip> サイズは最大の項目のサイズまたは指定された最小サイズになります。

  - <xref:System.Windows.Forms.ToolStrip.AutoSize%2A>がで、がの場合 `false` <xref:System.Windows.Forms.ToolStripItemImageScaling> <xref:System.Windows.Forms.ToolStripItemImageScaling.None> 、イメージも <xref:System.Windows.Forms.ToolStrip> スケーリングも実行されません。

#### <a name="alignment"></a>Alignment

プロパティの値によって <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 、項目が表示されるの末尾が決まり <xref:System.Windows.Forms.ToolStrip> ます。 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>プロパティは、のレイアウトスタイル <xref:System.Windows.Forms.ToolStrip> がスタックオーバーフローの値のいずれかに設定されている場合にのみ機能します。

項目は、項目 <xref:System.Windows.Forms.ToolStrip> コレクション内で項目が表示される順序でに配置されます。 項目のレイアウトをプログラムで変更するには、メソッドを使用して <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> コレクション内の項目を移動します。 このメソッドは項目を移動しますが、重複しません。

#### <a name="text-and-image-relationship"></a>テキストとイメージの関係

プロパティは、の <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> テキストに対するイメージの相対的な配置を定義し <xref:System.Windows.Forms.ToolStripItem> ます。 イメージ、テキスト、またはその両方を持たない項目は特殊なケースとして扱われるので、によって欠落している <xref:System.Windows.Forms.ToolStripItem> 要素の空白の位置が表示されません。

#### <a name="display-style"></a>表示スタイル

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 項目のテキストとイメージのプロパティの値を設定し、必要なものだけを表示することができます。 これは通常、別のコンテキストで同じ項目を表示するときに、表示スタイルのみを変更するために使用されます。

## <a name="accessory-classes"></a>アクセサリクラス

その他のさまざまな機能を提供するクラスは次のとおりです。

- <xref:System.Windows.Forms.ToolStripManager><xref:System.Windows.Forms.ToolStrip>マージ、設定、レンダラーオプションなど、アプリケーション全体に関連するタスクをサポートします。

- <xref:System.Windows.Forms.ToolStripRenderer> では、特定のスタイルまたはテーマを簡単に適用でき <xref:System.Windows.Forms.ToolStrip> ます。

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 置き換え可能なカラーテーブル () に基づいて、ペンとブラシを作成し <xref:System.Windows.Forms.ProfessionalColorTable> ます。

- <xref:System.Windows.Forms.ToolStripSystemRenderer> アプリケーションにシステムカラーとフラットな視覚スタイルを適用 <xref:System.Windows.Forms.ToolStrip> します。

- <xref:System.Windows.Forms.ToolStripContainer> はに似てい <xref:System.Windows.Forms.SplitContainer> ます。 この例では、4つのドッキングされたサイドパネル (のインスタンス <xref:System.Windows.Forms.ToolStripPanel> ) と1つの中央のパネル (のインスタンス) を使用して <xref:System.Windows.Forms.ToolStripContentPanel> 、一般的な配置を作成します。 サイドパネルを削除することはできませんが、非表示にすることはできます。 中央のパネルを削除したり非表示にしたりすることはできません。 サイドパネルには、1つまたは複数のコントロールを配置できます。また、中央のパネルを使用して他のコントロールを配置することもでき <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> ます。 また、では、 <xref:System.Windows.Forms.ToolStripContentPanel> フォームの本文に対するレンダラーサポートを一貫した外観で利用することもできます。 <xref:System.Windows.Forms.ToolStripContainer> では、マルチドキュメントインターフェイス (MDI) はサポートされていません。

- <xref:System.Windows.Forms.ToolStripPanel> コントロールを移動および整列するための領域を提供 <xref:System.Windows.Forms.ToolStrip> します。 パネルは1つしか使用できません。選択すると、 <xref:System.Windows.Forms.ToolStripPanel> MDI シナリオで適切に動作します。

## <a name="see-also"></a>関連項目

- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
- [ToolStrip テクノロジの概要](toolstrip-technology-summary.md)
- [ToolStrip コントロール](toolstrip-control-windows-forms.md)
- [MenuStrip コントロール](menustrip-control-windows-forms.md)
- [StatusStrip コントロール](statusstrip-control.md)
- [ContextMenuStrip コントロール](contextmenustrip-control.md)
- [BindingNavigator コントロール](bindingnavigator-control-windows-forms.md)
