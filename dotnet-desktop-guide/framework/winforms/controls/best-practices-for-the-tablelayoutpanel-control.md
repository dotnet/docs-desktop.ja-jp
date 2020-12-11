---
title: TableLayoutPanel コントロールの推奨される手順
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981092"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>TableLayoutPanel コントロールの推奨される手順
<xref:System.Windows.Forms.TableLayoutPanel>コントロールには、Windows フォームでを使用する前に慎重に検討する必要がある強力なレイアウト機能が用意されています。

## <a name="recommendations"></a>推奨事項
 次の推奨事項は、コントロールを <xref:System.Windows.Forms.TableLayoutPanel> 最大限に活用するのに役立ちます。

### <a name="targeted-use"></a>対象の使用
 コントロールは控えめに使用して <xref:System.Windows.Forms.TableLayoutPanel> ください。 サイズ変更可能なレイアウトが必要なすべての状況で使用しないでください。 次の一覧では、コントロールを使用する場合の利点を最大限に活用できるレイアウトについて説明し <xref:System.Windows.Forms.TableLayoutPanel> ます。

- フォームの複数の部分が相互に比例してサイズ変更されるレイアウト。

- 設定に基づいてユーザーがカスタマイズ可能なフィールドを追加または削除するデータ入力フォームなど、実行時に動的に変更または生成されるレイアウト。

- 全体の固定サイズのままにする必要があるレイアウト。 たとえば、800 x 600 よりも小さくする必要があるのに、ローカライズされた文字列をサポートする必要があるダイアログボックスがあるとします。

 次の一覧では、コントロールを使用することによる利点が得られないレイアウトについて説明し <xref:System.Windows.Forms.TableLayoutPanel> ます。

- ラベルの1つの列とテキスト入力領域の1つの列でなる単純なデータ入力フォーム。

- サイズ変更が発生したときに使用可能なすべての領域を埋める必要がある、1つの大きな表示領域があるフォーム。 この例として、1つのコントロールを表示するフォームが <xref:System.Windows.Forms.PropertyGrid> あります。 この場合は、フォームのサイズが変更されたときに他のものが展開されないため、アンカーを使用します。

 コントロールに必要なコントロールを慎重に選択して <xref:System.Windows.Forms.TableLayoutPanel> ください。 アンカーを使用してテキストを30% 拡張する余地がある場合は、プロパティのみを使用することを検討してください <xref:System.Windows.Forms.Control.Anchor%2A> 。 レイアウトに必要な領域を見積もることができる場合は、 <xref:System.Windows.Forms.Control.Dock%2A> との使用 <xref:System.Windows.Forms.Control.Anchor%2A> は、残りの領域と動作の詳細を推定するよりも簡単です <xref:System.Windows.Forms.Control.AutoSize%2A> 。

 一般に、コントロールを使用してレイアウトをデザインする場合は、 <xref:System.Windows.Forms.TableLayoutPanel> デザインをできるだけ単純なものにしてください。

### <a name="use-the-document-outline-window"></a>[ドキュメントアウトライン] ウィンドウを使用する
 [ドキュメントアウトライン] ウィンドウには、レイアウトのツリービューが表示されます。このビューを使用して、コントロールの z オーダーと親子関係を操作できます。 [ **表示] メニュー** の [ **その他のウィンドウ**] をポイントし、[ **ドキュメントアウトライン**] を選択します。

### <a name="avoid-nesting"></a>入れ子の回避
 <xref:System.Windows.Forms.TableLayoutPanel>コントロール内で他のコントロールを入れ子にしないように <xref:System.Windows.Forms.TableLayoutPanel> します。 入れ子になったレイアウトのデバッグは困難な場合があります。

### <a name="avoid-visual-inheritance"></a>ビジュアルの継承を避ける
 コントロールは、visual <xref:System.Windows.Forms.TableLayoutPanel> Studio の Windows フォームデザイナーでのビジュアル継承をサポートしていません。 <xref:System.Windows.Forms.TableLayoutPanel>派生クラスのコントロールは、デザイン時に "locked" として表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
