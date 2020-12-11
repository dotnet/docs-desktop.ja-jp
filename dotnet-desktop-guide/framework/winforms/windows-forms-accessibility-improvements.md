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
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a><span data-ttu-id="5b3f4-103">.NET Core 3.0 の Windows フォームコントロールでのアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="5b3f4-103">Accessibility improvements in Windows Forms controls for .NET Core 3.0</span></span>

<span data-ttu-id="5b3f4-104">Windows フォームは、Windows フォームのお客様のサポートを強化するために、ユーザー補助テクノロジとの連携の向上を続けています。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-104">Windows Forms is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="5b3f4-105">次のような改善点があります。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-105">These improvements include the following changes:</span></span>

- <span data-ttu-id="5b3f4-106">ユーザー補助クライアントアプリケーション (ナレーターを含む) との相互作用のさまざまな領域の変更。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-106">Changes in various areas of interaction with accessibility client applications, including Narrator.</span></span>
- <span data-ttu-id="5b3f4-107">アクセス可能な階層の変更 (UI オートメーション ツリー間の移動の改善)。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>
- <span data-ttu-id="5b3f4-108">キーボードナビゲーションの変更点</span><span class="sxs-lookup"><span data-stu-id="5b3f4-108">Changes in keyboard navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b3f4-109">.NET Framework 4.8 で .NET Framework 4.7.1 で行われたアクセシビリティの変更は、.NET Core 3.0 以降に含まれており、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-109">Accessibility changes made in .NET Framework 4.7.1 through .NET Framework 4.8 are included in .NET Core 3.0 and above, and are enabled by default.</span></span> <span data-ttu-id="5b3f4-110">.NET Framework は、アプリケーションが新しいアクセシビリティ動作をオプトアウトすることを許可する互換性スイッチをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-110">The .NET Framework supported compatibility switches that allowed applications to opt out of the new accessibility behavior.</span></span> <span data-ttu-id="5b3f4-111">一方、.NET Core はこれらの設定をサポートしていないため、アプリケーションはユーザー補助機能の動作を無効にできません。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-111">On the other hand, .NET Core doesn't support these settings and doesn't allow applications to opt out of accessibility behavior.</span></span>
  
<span data-ttu-id="5b3f4-112">.NET Core 3.0 以降では、Windows フォームアプリケーションは、追加の構成なしで (.NET Framework 4.7.1-4.8 で導入された) すべての新しいユーザー補助機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-112">Starting with .NET Core 3.0, Windows Forms applications benefit from all the new accessibility features (introduced in .NET Framework 4.7.1 - 4.8) without additional configuration.</span></span>

## <a name="listbox-accessibility-support"></a><span data-ttu-id="5b3f4-113">ListBox のアクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-113">ListBox Accessibility support</span></span>

<span data-ttu-id="5b3f4-114">コントロールには、次の変更が適用され <xref:System.Windows.Forms.ListBox> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-114">The following changes apply to the <xref:System.Windows.Forms.ListBox> control:</span></span>

- <span data-ttu-id="5b3f4-115">UI オートメーションによるコントロールのサポートを有効にしました `ListBox` 。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-115">Enabled UI Automation support for `ListBox` control.</span></span>
- <span data-ttu-id="5b3f4-116">`ListBox`を項目に追加することによってユーザー補助機能のサポートが強化されました <xref:System.Windows.Automation.ScrollItemPattern> `ListBox` 。また、ユーザー補助イベントの発生と処理および項目間のナレーターナビゲーションを強化します (capslock キーは正しくありません。また、意図せずにコントロール外のナビゲーションをスローすることもありません)。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-116">Improved `ListBox` accessibility support by adding the <xref:System.Windows.Automation.ScrollItemPattern> to `ListBox` items and by enhancing the accessibility event raising and handling and Narrator navigation through the items (caps lock navigation isn't correct and doesn't throw the navigation outside the control unintentionally).</span></span>

## <a name="checkedlistbox-accessibility-support"></a><span data-ttu-id="5b3f4-117">CheckedListBox のユーザー補助機能のサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-117">CheckedListBox Accessibility support</span></span>

<span data-ttu-id="5b3f4-118">コントロールには、次の変更が適用され <xref:System.Windows.Forms.CheckedListBox> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-118">The following changes apply to the <xref:System.Windows.Forms.CheckedListBox> control:</span></span>

- <span data-ttu-id="5b3f4-119">`CheckedListBox`エントリのアクセシビリティプロパティによって指定された境界を修正しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-119">Corrected `CheckedListBox` Bounds provided by accessibility properties for entries.</span></span>
- <span data-ttu-id="5b3f4-120">全体的 `ListBox` およびアクセシビリティの向上 `CheckedListBox` : プロパティ値とイベントモデルを修正しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-120">Improved overall `ListBox` and `CheckedListBox` accessibility: corrected property values and event model.</span></span>

## <a name="combobox-accessibility-support"></a><span data-ttu-id="5b3f4-121">ComboBox のアクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-121">ComboBox Accessibility support</span></span>

<span data-ttu-id="5b3f4-122">コントロールには、次の変更が適用され <xref:System.Windows.Forms.ComboBox> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-122">The following changes apply to the <xref:System.Windows.Forms.ComboBox> control:</span></span>

- <span data-ttu-id="5b3f4-123">項目のアクセシビリティオブジェクトを取得して項目の Id を生成できるようにするプロセスを更新しました `ComboBox` 。これは、項目からハッシュコードを取得するのではなく、関数がオーバーライドされた場合には安全ではない可能性があり <xref:System.Object.GetHashCode%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-123">Updated the process of getting `ComboBox` items' accessibility objects to enable generating IDs for items instead of getting hash codes from items, which may be unsafe in case the <xref:System.Object.GetHashCode%2A> function is overridden.</span></span>

## <a name="datagridview-accessibility-support"></a><span data-ttu-id="5b3f4-124">DataGridView のアクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-124">DataGridView Accessibility support</span></span>

<span data-ttu-id="5b3f4-125">コントロールには、次の変更が適用され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-125">The following changes apply to the <xref:System.Windows.Forms.DataGridView> control:</span></span>

- <span data-ttu-id="5b3f4-126">`DataGridView.Bounds`列、行、セル、および対応するヘッダーのアクセシビリティプロパティによって提供される修正により、外接する四角形計算のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-126">Corrected `DataGridView.Bounds` provided by accessibility properties for columns, rows, cells and corresponding headers, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="5b3f4-127">すべてのアクセシビリティの境界は、コントロール全体の境界とビューポートを考慮して、正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-127">All accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="5b3f4-128">`Value.IsReadOnly`アクセス可能なクライアントアプリケーションに対して提供されるプロパティ値を修正しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-128">Corrected `Value.IsReadOnly` property value providing for accessible client applications.</span></span> <span data-ttu-id="5b3f4-129">これで、プロパティにセルの正しい状態が表示されるようになりました `IsReadOnly` 。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-129">The property now shows correct `IsReadOnly` status for cells.</span></span>
- <span data-ttu-id="5b3f4-130">最初のセル変更のイベント発生に関する問題を修正して <xref:System.Windows.Forms.DataGridView.CellParsing> います。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-130">Fixed the issue with <xref:System.Windows.Forms.DataGridView.CellParsing> event raising for the first cell change.</span></span> <span data-ttu-id="5b3f4-131">セル値は、最初のコントロール操作を含め、問題なく変更でき `DataGridView` ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-131">Cell value can be changed without any issues including the first `DataGridView` control interaction.</span></span>
- <span data-ttu-id="5b3f4-132">`DataGridView`Windows ハイコントラストテーマを使用する場合の背景色のコントラストが向上しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-132">Improved `DataGridView` background color contrast when using Windows High Contrast themes.</span></span> <span data-ttu-id="5b3f4-133">`DataGridView`HC # 1、HC # 2、および HC Black のテーマを使用するときに、既定の背景色が変更されました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-133">Changed `DataGridView` default back color when using HC#1, HC#2, and HC Black themes.</span></span>

## <a name="propertygrid-accessibility-support"></a><span data-ttu-id="5b3f4-134">PropertyGrid のユーザー補助機能のサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-134">PropertyGrid Accessibility support</span></span>

<span data-ttu-id="5b3f4-135">コントロールには、次の変更が適用され <xref:System.Windows.Forms.PropertyGrid> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-135">The following changes apply to the <xref:System.Windows.Forms.PropertyGrid> control:</span></span>

- <span data-ttu-id="5b3f4-136">`PropertyGrid.Bounds`グリッドエントリのアクセシビリティプロパティによって提供され、外接する四角形計算のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-136">Corrected `PropertyGrid.Bounds` provided by accessibility properties for grid entries, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="5b3f4-137">現時点では、すべてのアクセシビリティの境界は、コントロール全体の境界とビューポートを考慮して正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-137">For now all accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="5b3f4-138">コントロールの型名を含まないように、アクセス可能な名前とサブコントロールの説明を修正しました。また、コントロールの種類名が二重にアナウンスされないようにします。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-138">Corrected accessible names and descriptions of subcontrols to not include control type names and to avoid double announcement for control type names.</span></span>

## <a name="toolstrip-accessibility-support"></a><span data-ttu-id="5b3f4-139">ToolStrip アクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-139">ToolStrip Accessibility support</span></span>

<span data-ttu-id="5b3f4-140">コントロールには、次の変更が適用され <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-140">The following changes apply to the <xref:System.Windows.Forms.ToolStrip> control:</span></span>

- <span data-ttu-id="5b3f4-141">`ToolStrip`、、およびの各項目によるナビゲーションが改善されました `MenuStrip` `StatusStrip` 。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-141">Improved navigation through `ToolStrip`, `MenuStrip`, and `StatusStrip` items.</span></span> <span data-ttu-id="5b3f4-142">Shift + tab キーを押し `ToolStrip` `MenuStrip` たときに shift + tab キーを押すとメニュー項目が戻る、shift + tab キーを押すと、下のメニュー要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-142">Corrected `ToolStrip` and `MenuStrip` shift-tab navigation, back-looping the menu items when shift-tab up-arrow is pressed, which navigates to the bottom menu element.</span></span>
- <span data-ttu-id="5b3f4-143">`MenuStrip`アクセス可能なナビゲーションが改善され、メニューを使用して ' MenuItem ' ではなく ' menu ' 型のサブメニューを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-143">Improved `MenuStrip` accessible navigation, corrected menu accessible control types for submenus to make submenus of type 'Menu' instead of 'MenuItem'.</span></span>

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a><span data-ttu-id="5b3f4-144">Printプレビューコントロールと Printプレビューダイアログのユーザー補助機能のサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-144">PrintPreviewControl and PrintPreviewDialog Accessibility support</span></span>

<span data-ttu-id="5b3f4-145">印刷コントロールには、次の変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-145">The following changes apply to the print controls:</span></span>

- <span data-ttu-id="5b3f4-146">メニュー項目を使用したユーザー補助ナビゲーション (ナレーターナビゲーションを含む) の向上。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-146">Improved accessible navigation (including Narrator navigation) through menu items.</span></span>
- <span data-ttu-id="5b3f4-147">ハイコントラストテーマのサポートが改善され、コントロール要素の比較が向上しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-147">Improved High Contrast themes support and made the control element more contrasted.</span></span>

## <a name="stringcollectioneditor-accessibility-support"></a><span data-ttu-id="5b3f4-148">StringCollectionEditor のユーザー補助機能のサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-148">StringCollectionEditor Accessibility support</span></span>

<span data-ttu-id="5b3f4-149">Windows フォームデザイナーでは、ユーザー補助機能のサポートが強化された文字列コレクションエディターが使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-149">Windows Forms designer now uses the string collection editor with improved accessibility support.</span></span>

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a><span data-ttu-id="5b3f4-150">MonthCalendar アクセシビリティサポート (.NET Core 3.1 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="5b3f4-150">MonthCalendar Accessibility support (available in .NET Core 3.1)</span></span>

<span data-ttu-id="5b3f4-151">コントロールには、次の変更が適用され <xref:System.Windows.Forms.MonthCalendar> ます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-151">The following changes apply to the <xref:System.Windows.Forms.MonthCalendar> control:</span></span>

- <span data-ttu-id="5b3f4-152">Ui オートメーションサーバープロバイダーを追加し `MonthCalendar` て、コントロールを追加し、Ui オートメーショングリッドパターンとテーブルパターンプロバイダーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-152">Added UI Automation server providers to `MonthCalendar` control, added UI Automation Grid pattern and Table pattern providers.</span></span>
- <span data-ttu-id="5b3f4-153">コントロールにアクセス可能な名前を定義する前のラベルコントロールがコントロールにある場合を除き、 _テーブル_ にアクセス可能なコントロール _型をに_ 変更しました `MonthCalendar` 。ただし、この特定のケースでは、アクセス可能なコントロール型は `MonthCalendar` _テーブル_ になります。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-153">Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.</span></span>
- <span data-ttu-id="5b3f4-154">コントロールの選択された日付のアナウンスが向上しました `MonthCalendar` 。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-154">Improved announcement of selected date for `MonthCalendar` control.</span></span>
- <span data-ttu-id="5b3f4-155">`MonthCalendar`スクリーンリーダーやその他のユーザー補助ツールのコントロールサポートを強化しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-155">Improved `MonthCalendar` control support for screen readers and other accessibility tools.</span></span> <span data-ttu-id="5b3f4-156">この時点で、ユーザーは、コントロール要素をナビゲートし、キーボードのみの入力を使用してこれらの要素と対話できます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-156">At this moment, users can navigate the control elements and interact with these elements using keyboard-only input.</span></span> <span data-ttu-id="5b3f4-157">ナレーターでは、CAPSLOCK キーを使用してコントロール要素を移動し、Enter + Enter キーを押して要素の既定のアクションを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-157">With Narrator, use CAPS + arrow keys to navigation through the control elements and CAPS + Enter to invoke element default action.</span></span>
- <span data-ttu-id="5b3f4-158">`MonthCalendar`フォーカスされた四角形を使用した子要素間の方向キーのナビゲーションが改善されました: ナレーター用の青いフォーカス四角形。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-158">Improved arrow key navigation across `MonthCalendar` child elements with a focusing rectangle: blue focus rectangle for Narrator.</span></span>
- <span data-ttu-id="5b3f4-159">`MonthCalendar` `MonthCalendar` 指定された座標で子のアクセス可能な要素を取得できるようにするコントロール要素のヒットテストアクションのアクセシビリティが向上しました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-159">Improved accessibility for hit test action for `MonthCalendar` control elements to allow getting `MonthCalendar` child accessible element by provided coordinates.</span></span>

## <a name="tooltips-accessibility-available-in-net-core-31"></a><span data-ttu-id="5b3f4-160">ツールヒントアクセシビリティ (.NET Core 3.1 で使用可能)</span><span class="sxs-lookup"><span data-stu-id="5b3f4-160">ToolTips accessibility (available in .NET Core 3.1)</span></span>

- <span data-ttu-id="5b3f4-161">NVDA やナレーターなどのスクリーンリーダーアプリケーションで、ツールヒントテキストをアナウンスする機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-161">Added ability to announce a tooltip text by screen reader applications such as NVDA and Narrator.</span></span> <span data-ttu-id="5b3f4-162">スクリーンリーダーアプリケーションで、ツールヒントを表示するように構成されている Windows フォームコントロールのキーボードまたはマウスのツールヒントのテキストを発表できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-162">Screen reader application can now announce the text of keyboard or mouse tooltip of any Windows Forms control that configured to show tooltips.</span></span>

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a><span data-ttu-id="5b3f4-163">UI オートメーションによる DataGridView、PropertyGrid、ListBox、ComboBox、ToolStrip、およびその他のコントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="5b3f4-163">UI automation support for DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip, and other controls</span></span>

<span data-ttu-id="5b3f4-164">UI オートメーションのサポートは実行時にコントロールに対して有効になっていますが、デザイン時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-164">UI Automation support is enabled for controls at runtime but isn't used during design time.</span></span> <span data-ttu-id="5b3f4-165">UI オートメーションの概要については、「[UI オートメーションの概要](/dotnet/framework/ui-automation/ui-automation-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-165">For an overview of UI automation, see the [UI Automation Overview](/dotnet/framework/ui-automation/ui-automation-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b3f4-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b3f4-166">See also</span></span>

- <span data-ttu-id="5b3f4-167">[ユーザー補助のベストプラクティス](/dotnet/framework/ui-automation/accessibility-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="5b3f4-167">[Accessibility Best Practices](/dotnet/framework/ui-automation/accessibility-best-practices).</span></span>
