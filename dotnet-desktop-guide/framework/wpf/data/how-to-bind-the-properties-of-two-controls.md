---
title: '方法: 2 つのコントロールのプロパティをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 28b5f65a57fc210f3d405020daa0d75c28b934c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974496"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="05fce-102">方法: 2 つのコントロールのプロパティをバインドする</span><span class="sxs-lookup"><span data-stu-id="05fce-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="05fce-103">この例では、<xref:System.Windows.Data.Binding.ElementName%2A> プロパティを使用して、インスタンス化された 1 つのコントロールのプロパティを別のコントロールのプロパティにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05fce-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="05fce-104">例</span><span class="sxs-lookup"><span data-stu-id="05fce-104">Example</span></span>

<span data-ttu-id="05fce-105">次の例では、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Panel.Background%2A> プロパティを <xref:System.Windows.Controls.ComboBox> の [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) プロパティにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05fce-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="05fce-106">この例をレンダリングすると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="05fce-106">When this example is rendered it looks like the following:</span></span>

![値 Green が選択され、緑色の四角形が表示されているコンボ ボックスのスクリーンショット。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="05fce-108">バインディング ターゲット プロパティ (この例では <xref:System.Windows.Controls.Panel.Background%2A> プロパティ) は、依存関係プロパティである必要があります。</span><span class="sxs-lookup"><span data-stu-id="05fce-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="05fce-109">詳しくは、「[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="05fce-109">For more information, see [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="05fce-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="05fce-110">See also</span></span>

- [<span data-ttu-id="05fce-111">バインディング ソースを指定する</span><span class="sxs-lookup"><span data-stu-id="05fce-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="05fce-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="05fce-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
