---
title: アクセシビリティの機能強化の Windows フォーム
description: .NET Core Windows フォームが .NET Framework Windows フォームと比較してアクセシビリティを向上させる方法について説明します。
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 4dc477cebf35435ff2122ce21644135848985d07
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974713"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>.NET Core 3.0 の Windows フォームコントロールでのアクセシビリティの向上

Windows フォームは、Windows フォームのお客様のサポートを強化するために、ユーザー補助テクノロジとの連携の向上を続けています。 次のような改善点があります。

- ユーザー補助クライアントアプリケーション (ナレーターを含む) との相互作用のさまざまな領域の変更。
- アクセス可能な階層の変更 (UI オートメーション ツリー間の移動の改善)。
- キーボードナビゲーションの変更点

> [!IMPORTANT]
> .NET Framework 4.8 で .NET Framework 4.7.1 で行われたアクセシビリティの変更は、.NET Core 3.0 以降に含まれており、既定で有効になっています。 .NET Framework は、アプリケーションが新しいアクセシビリティ動作をオプトアウトすることを許可する互換性スイッチをサポートしています。 一方、.NET Core はこれらの設定をサポートしていないため、アプリケーションはユーザー補助機能の動作を無効にできません。
  
.NET Core 3.0 以降では、Windows フォームアプリケーションは、追加の構成なしで (.NET Framework 4.7.1-4.8 で導入された) すべての新しいユーザー補助機能を利用できます。

## <a name="listbox-accessibility-support"></a>ListBox のアクセシビリティサポート

コントロールには、次の変更が適用され <xref:System.Windows.Forms.ListBox> ます。

- UI オートメーションによるコントロールのサポートを有効にしました `ListBox` 。
- `ListBox`を項目に追加することによってユーザー補助機能のサポートが強化されました <xref:System.Windows.Automation.ScrollItemPattern> `ListBox` 。また、ユーザー補助イベントの発生と処理および項目間のナレーターナビゲーションを強化します (capslock キーは正しくありません。また、意図せずにコントロール外のナビゲーションをスローすることもありません)。

## <a name="checkedlistbox-accessibility-support"></a>CheckedListBox のユーザー補助機能のサポート

コントロールには、次の変更が適用され <xref:System.Windows.Forms.CheckedListBox> ます。

- `CheckedListBox`エントリのアクセシビリティプロパティによって指定された境界を修正しました。
- 全体的 `ListBox` およびアクセシビリティの向上 `CheckedListBox` : プロパティ値とイベントモデルを修正しました。

## <a name="combobox-accessibility-support"></a>ComboBox のアクセシビリティサポート

コントロールには、次の変更が適用され <xref:System.Windows.Forms.ComboBox> ます。

- 項目のアクセシビリティオブジェクトを取得して項目の Id を生成できるようにするプロセスを更新しました `ComboBox` 。これは、項目からハッシュコードを取得するのではなく、関数がオーバーライドされた場合には安全ではない可能性があり <xref:System.Object.GetHashCode%2A> ます。

## <a name="datagridview-accessibility-support"></a>DataGridView のアクセシビリティサポート

コントロールには、次の変更が適用され <xref:System.Windows.Forms.DataGridView> ます。

- `DataGridView.Bounds`列、行、セル、および対応するヘッダーのアクセシビリティプロパティによって提供される修正により、外接する四角形計算のパフォーマンスが向上しました。 すべてのアクセシビリティの境界は、コントロール全体の境界とビューポートを考慮して、正しく表示されます。
- `Value.IsReadOnly`アクセス可能なクライアントアプリケーションに対して提供されるプロパティ値を修正しました。 これで、プロパティにセルの正しい状態が表示されるようになりました `IsReadOnly` 。
- 最初のセル変更のイベント発生に関する問題を修正して <xref:System.Windows.Forms.DataGridView.CellParsing> います。 セル値は、最初のコントロール操作を含め、問題なく変更でき `DataGridView` ます。
- `DataGridView`Windows ハイコントラストテーマを使用する場合の背景色のコントラストが向上しました。 `DataGridView`HC # 1、HC # 2、および HC Black のテーマを使用するときに、既定の背景色が変更されました。

## <a name="propertygrid-accessibility-support"></a>PropertyGrid のユーザー補助機能のサポート

コントロールには、次の変更が適用され <xref:System.Windows.Forms.PropertyGrid> ます。

- `PropertyGrid.Bounds`グリッドエントリのアクセシビリティプロパティによって提供され、外接する四角形計算のパフォーマンスが向上しました。 現時点では、すべてのアクセシビリティの境界は、コントロール全体の境界とビューポートを考慮して正しく表示されます。
- コントロールの型名を含まないように、アクセス可能な名前とサブコントロールの説明を修正しました。また、コントロールの種類名が二重にアナウンスされないようにします。

## <a name="toolstrip-accessibility-support"></a>ToolStrip アクセシビリティサポート

コントロールには、次の変更が適用され <xref:System.Windows.Forms.ToolStrip> ます。

- `ToolStrip`、、およびの各項目によるナビゲーションが改善されました `MenuStrip` `StatusStrip` 。 Shift + tab キーを押し `ToolStrip` `MenuStrip` たときに shift + tab キーを押すとメニュー項目が戻る、shift + tab キーを押すと、下のメニュー要素に移動します。
- `MenuStrip`アクセス可能なナビゲーションが改善され、メニューを使用して ' MenuItem ' ではなく ' menu ' 型のサブメニューを作成できるようになりました。

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>Printプレビューコントロールと Printプレビューダイアログのユーザー補助機能のサポート

印刷コントロールには、次の変更が適用されます。

- メニュー項目を使用したユーザー補助ナビゲーション (ナレーターナビゲーションを含む) の向上。
- ハイコントラストテーマのサポートが改善され、コントロール要素の比較が向上しました。

## <a name="stringcollectioneditor-accessibility-support"></a>StringCollectionEditor のユーザー補助機能のサポート

Windows フォームデザイナーでは、ユーザー補助機能のサポートが強化された文字列コレクションエディターが使用されるようになりました。

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>MonthCalendar アクセシビリティサポート (.NET Core 3.1 で利用可能)

コントロールには、次の変更が適用され <xref:System.Windows.Forms.MonthCalendar> ます。

- Ui オートメーションサーバープロバイダーを追加し `MonthCalendar` て、コントロールを追加し、Ui オートメーショングリッドパターンとテーブルパターンプロバイダーを追加しました。
- コントロールにアクセス可能な名前を定義する前のラベルコントロールがコントロールにある場合を除き、 _テーブル_ にアクセス可能なコントロール _型をに_ 変更しました `MonthCalendar` 。ただし、この特定のケースでは、アクセス可能なコントロール型は `MonthCalendar` _テーブル_ になります。
- コントロールの選択された日付のアナウンスが向上しました `MonthCalendar` 。
- `MonthCalendar`スクリーンリーダーやその他のユーザー補助ツールのコントロールサポートを強化しました。 この時点で、ユーザーは、コントロール要素をナビゲートし、キーボードのみの入力を使用してこれらの要素と対話できます。 ナレーターでは、CAPSLOCK キーを使用してコントロール要素を移動し、Enter + Enter キーを押して要素の既定のアクションを呼び出すことができます。
- `MonthCalendar`フォーカスされた四角形を使用した子要素間の方向キーのナビゲーションが改善されました: ナレーター用の青いフォーカス四角形。
- `MonthCalendar` `MonthCalendar` 指定された座標で子のアクセス可能な要素を取得できるようにするコントロール要素のヒットテストアクションのアクセシビリティが向上しました。

## <a name="tooltips-accessibility-available-in-net-core-31"></a>ツールヒントアクセシビリティ (.NET Core 3.1 で使用可能)

- NVDA やナレーターなどのスクリーンリーダーアプリケーションで、ツールヒントテキストをアナウンスする機能が追加されました。 スクリーンリーダーアプリケーションで、ツールヒントを表示するように構成されている Windows フォームコントロールのキーボードまたはマウスのツールヒントのテキストを発表できるようになりました。

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>UI オートメーションによる DataGridView、PropertyGrid、ListBox、ComboBox、ToolStrip、およびその他のコントロールのサポート

UI オートメーションのサポートは実行時にコントロールに対して有効になっていますが、デザイン時には使用されません。 UI オートメーションの概要については、「[UI オートメーションの概要](/dotnet/framework/ui-automation/ui-automation-overview)」を参照してください。

## <a name="see-also"></a>関連項目

- [ユーザー補助のベストプラクティス](/dotnet/framework/ui-automation/accessibility-best-practices)。
