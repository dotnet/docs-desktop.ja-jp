---
title: '方法: メソッドにバインドする'
description: 次の例に従って、Windows Presentation Foundation (WPF) でオブジェクトのメソッドにバインドする方法を確認します。
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974492"
---
# <a name="how-to-bind-to-a-method"></a><span data-ttu-id="c5b81-103">方法: メソッドにバインドする</span><span class="sxs-lookup"><span data-stu-id="c5b81-103">How to: Bind to a Method</span></span>
<span data-ttu-id="c5b81-104">次の例では、<xref:System.Windows.Data.ObjectDataProvider> を使用してメソッドにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5b81-104">The following example shows how to bind to a method using <xref:System.Windows.Data.ObjectDataProvider>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5b81-105">例</span><span class="sxs-lookup"><span data-stu-id="c5b81-105">Example</span></span>  
 <span data-ttu-id="c5b81-106">この例では、`TemperatureScale` はメソッド `ConvertTemp` を持つクラスで、2 つのパラメーター (1 つは `double` でもう 1 つは `enum` 型 `TempType)`) を取得して、指定した値をある温度尺度から他の温度尺度へ変換します。</span><span class="sxs-lookup"><span data-stu-id="c5b81-106">In this example, `TemperatureScale` is a class that has a method `ConvertTemp`, which takes two parameters (one of `double` and one of the `enum` type `TempType)` and converts the given value from one temperature scale to another.</span></span> <span data-ttu-id="c5b81-107">次の例では、<xref:System.Windows.Data.ObjectDataProvider> を使用して `TemperatureScale` オブジェクトをインスタンス化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5b81-107">In the following example, an <xref:System.Windows.Data.ObjectDataProvider> is used to instantiate the `TemperatureScale` object.</span></span> <span data-ttu-id="c5b81-108">`ConvertTemp` メソッドは、2 つの指定したパラメーターで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c5b81-108">The `ConvertTemp` method is called with two specified parameters.</span></span>  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 <span data-ttu-id="c5b81-109">このメソッドはリソースとして使用可能となり、その結果にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="c5b81-109">Now that the method is available as a resource, you can bind to its results.</span></span> <span data-ttu-id="c5b81-110">次の例では、<xref:System.Windows.Controls.TextBox> の <xref:System.Windows.Controls.TextBox.Text%2A> プロパティと <xref:System.Windows.Controls.ComboBox> の <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> を、メソッドの 2 つのパラメーターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="c5b81-110">In the following example, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> of the <xref:System.Windows.Controls.ComboBox> are bound to the two parameters of the method.</span></span> <span data-ttu-id="c5b81-111">これにより、ユーザーは、変換する温度と変換前の温度尺度を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c5b81-111">This allows users to specify the temperature to convert and the temperature scale to convert from.</span></span> <span data-ttu-id="c5b81-112"><xref:System.Windows.Data.ObjectDataProvider> によってラップされたオブジェクト (`TemperatureScale` オブジェクト) のプロパティではなく、<xref:System.Windows.Data.ObjectDataProvider> インスタンスの <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> プロパティにバインドしているため、<xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> が `true` に設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5b81-112">Note that <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> is set to `true` because we are binding to the <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> property of the <xref:System.Windows.Data.ObjectDataProvider> instance and not properties of the object wrapped by the <xref:System.Windows.Data.ObjectDataProvider> (the `TemperatureScale` object).</span></span>  
  
 <span data-ttu-id="c5b81-113">ユーザーが <xref:System.Windows.Controls.TextBox> の内容または <xref:System.Windows.Controls.ComboBox> の選択を変更すると、最後の <xref:System.Windows.Controls.Label> の <xref:System.Windows.Controls.ContentControl.Content%2A> が更新されます。</span><span class="sxs-lookup"><span data-stu-id="c5b81-113">The <xref:System.Windows.Controls.ContentControl.Content%2A> of the last <xref:System.Windows.Controls.Label> updates when the user modifies the content of the <xref:System.Windows.Controls.TextBox> or the selection of the <xref:System.Windows.Controls.ComboBox>.</span></span>  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 <span data-ttu-id="c5b81-114">コンバーター `DoubleToString` は、方向が <xref:System.Windows.Data.IValueConverter.Convert%2A> のとき (バインディング ソースからバインディング ターゲット、これは <xref:System.Windows.Controls.TextBox.Text%2A> プロパティです) は double を受け取って string に変換し、方向が <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> のときは `string` を `double` に変換します。</span><span class="sxs-lookup"><span data-stu-id="c5b81-114">The converter `DoubleToString` takes a double and turns it into a string in the <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (from the binding source to binding target, which is the <xref:System.Windows.Controls.TextBox.Text%2A> property) and converts a `string` to a `double` in the <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.</span></span>  
  
 <span data-ttu-id="c5b81-115">`InvalidationCharacterRule` は、無効な文字をチェックする <xref:System.Windows.Controls.ValidationRule> です。</span><span class="sxs-lookup"><span data-stu-id="c5b81-115">The `InvalidationCharacterRule` is a <xref:System.Windows.Controls.ValidationRule> that checks for invalid characters.</span></span> <span data-ttu-id="c5b81-116">入力値が double 値でない場合は、既定のエラー テンプレート (<xref:System.Windows.Controls.TextBox> を囲む赤い境界線) がユーザーへの通知として表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5b81-116">The default error template, which is a red border around the <xref:System.Windows.Controls.TextBox>, appears to notify users when the input value is not a double value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b81-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5b81-117">See also</span></span>

- [<span data-ttu-id="c5b81-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="c5b81-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
- [<span data-ttu-id="c5b81-119">方法: 列挙値にバインドする</span><span class="sxs-lookup"><span data-stu-id="c5b81-119">Bind to an Enumeration</span></span>](how-to-bind-to-an-enumeration.md)
