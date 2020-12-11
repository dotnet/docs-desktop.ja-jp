---
title: 複雑なグリッドを作成する方法
description: グリッド コントロールを使用して、月間カレンダーのようなレイアウトを作成する方法の例。
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: ab5490d608b21fe8b29a078dc1f0147f038c27a3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985668"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="8dd47-103">複雑なグリッドを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8dd47-103">How to create a complex Grid</span></span>

<span data-ttu-id="8dd47-104">この例では、<xref:System.Windows.Controls.Grid> コントロールを使用して、月間カレンダーのようなレイアウトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8dd47-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="8dd47-105">例</span><span class="sxs-lookup"><span data-stu-id="8dd47-105">Example</span></span>

<span data-ttu-id="8dd47-106">次の例では、<xref:System.Windows.Controls.RowDefinition> クラスと <xref:System.Windows.Controls.ColumnDefinition> クラスを使用して、8 つの行と 8 つの列が定義されます。</span><span class="sxs-lookup"><span data-stu-id="8dd47-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="8dd47-107"><xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> と <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> 添付プロパティが <xref:System.Windows.Shapes.Rectangle> 要素と共に使用され、さまざまな列と行の背景が塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="8dd47-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="8dd47-108">この設計は、<xref:System.Windows.Controls.Grid> 内の各セルに複数の要素が存在できるため可能です。これは、<xref:System.Windows.Controls.Grid> と <xref:System.Windows.Documents.Table> の基本的な違いです。</span><span class="sxs-lookup"><span data-stu-id="8dd47-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="8dd47-109">この例では、垂直方向のグラデーションの使用により列と行が <xref:System.Windows.Shapes.Shape.Fill%2A> され、カレンダーの視覚表示と読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="8dd47-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="8dd47-110">スタイル設定された <xref:System.Windows.Controls.TextBlock> 要素により、日付と曜日が表されます。</span><span class="sxs-lookup"><span data-stu-id="8dd47-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="8dd47-111"><xref:System.Windows.Controls.TextBlock> 要素は、アプリケーションのスタイル内で定義されている <xref:System.Windows.FrameworkElement.Margin%2A> プロパティと配置プロパティを使用して、セル内に絶対位置で配置されます。</span><span class="sxs-lookup"><span data-stu-id="8dd47-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="8dd47-112">次の図は、結果であるコントロール、つまりカスタマイズ可能なカレンダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="8dd47-112">The following image shows the resulting control, a customizable calendar:</span></span>

![結果であるコントロールのスクリーン ショット](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="8dd47-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dd47-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="8dd47-115">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="8dd47-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="8dd47-116">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8dd47-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="8dd47-117">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="8dd47-117">Table Overview</span></span>](../advanced/table-overview.md)
