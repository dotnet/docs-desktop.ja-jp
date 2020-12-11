---
title: コントロールに属性を適用する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: f12b430d787b4b974e12902b2c17d3a35a09e468
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980971"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="5804f-102">方法: Windows フォーム コントロールに属性を適用する</span><span class="sxs-lookup"><span data-stu-id="5804f-102">How to: Apply Attributes in Windows Forms Controls</span></span>

<span data-ttu-id="5804f-103">デザイン環境と正しく対話し、実行時に正常に実行されるコンポーネントとコントロールを開発するには、クラスおよびメンバーに属性を正しく適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5804f-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5804f-104">例</span><span class="sxs-lookup"><span data-stu-id="5804f-104">Example</span></span>  

 <span data-ttu-id="5804f-105">次のコード例は、カスタムコントロールでいくつかの属性を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5804f-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="5804f-106">このコントロールは、単純なログ記録機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="5804f-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="5804f-107">コントロールがデータソースにバインドされると、コントロールにデータソースから送信された値が表示され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5804f-108">値がプロパティで指定された値を超えると `Threshold` 、 `ThresholdExceeded` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="5804f-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="5804f-109">は、 `AttributesDemoControl` クラスを使用して値をログに記録し `LogEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="5804f-110">クラスはテンプレートクラスであり、これは `LogEntry` ログに記録される型でパラメーター化されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5804f-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="5804f-111">たとえば、 `AttributesDemoControl` が型の値をログに記録している場合、各インスタンスは次のように宣言され、 `float` `LogEntry` 使用されます。</span><span class="sxs-lookup"><span data-stu-id="5804f-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="5804f-112">`LogEntry`は任意の型によってパラメーター化されるため、パラメーターの型を操作するにはリフレクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5804f-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="5804f-113">しきい値機能を機能させるには、パラメーターの型 `T` がインターフェイスを実装する必要があり <xref:System.IComparable> ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="5804f-114">をホストするフォームは、 `AttributesDemoControl` パフォーマンスカウンターを定期的に照会します。</span><span class="sxs-lookup"><span data-stu-id="5804f-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="5804f-115">各値は、適切な型のにパッケージ化され、 `LogEntry` フォームのに追加され <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="5804f-116">は、 `AttributesDemoControl` データバインディングを通じて値を受け取り、コントロールの値を表示し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="5804f-117">最初のコード例は、の `AttributesDemoControl` 実装です。</span><span class="sxs-lookup"><span data-stu-id="5804f-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="5804f-118">2番目のコード例は、を使用するフォームを示して `AttributesDemoControl` います。</span><span class="sxs-lookup"><span data-stu-id="5804f-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="5804f-119">クラスレベルの属性</span><span class="sxs-lookup"><span data-stu-id="5804f-119">Class-level Attributes</span></span>  

 <span data-ttu-id="5804f-120">一部の属性はクラスレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="5804f-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="5804f-121">次のコード例は、Windows フォームコントロールに一般的に適用される属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="5804f-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="5804f-122">TypeConverter 属性</span><span class="sxs-lookup"><span data-stu-id="5804f-122">TypeConverter Attribute</span></span>  

 <span data-ttu-id="5804f-123"><xref:System.ComponentModel.TypeConverterAttribute> は、一般的に使用されるもう1つのクラスレベルの属性です。</span><span class="sxs-lookup"><span data-stu-id="5804f-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="5804f-124">クラスの使用例を次のコード例に示し `LogEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="5804f-125">この例では、という型のの実装も示して <xref:System.ComponentModel.TypeConverter> `LogEntry` `LogEntryTypeConverter` います。</span><span class="sxs-lookup"><span data-stu-id="5804f-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="5804f-126">メンバーレベルの属性</span><span class="sxs-lookup"><span data-stu-id="5804f-126">Member-level Attributes</span></span>  

 <span data-ttu-id="5804f-127">一部の属性は、メンバーレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="5804f-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="5804f-128">次のコード例は、Windows フォームコントロールのプロパティに一般的に適用されるいくつかの属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="5804f-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="5804f-129">AmbientValue 属性</span><span class="sxs-lookup"><span data-stu-id="5804f-129">AmbientValue Attribute</span></span>  

 <span data-ttu-id="5804f-130">次の例は、を示し、 <xref:System.ComponentModel.AmbientValueAttribute> デザイン環境との対話をサポートするコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="5804f-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="5804f-131">この相互作用は、" *アンビエント*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5804f-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="5804f-132">Databinding 属性</span><span class="sxs-lookup"><span data-stu-id="5804f-132">Databinding Attributes</span></span>  

 <span data-ttu-id="5804f-133">次の例は、複合データバインディングの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="5804f-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="5804f-134">前に示したクラスレベルでは、 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> `DataSource` `DataMember` データバインディングに使用するプロパティとプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5804f-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="5804f-135">は、 <xref:System.ComponentModel.AttributeProviderAttribute> プロパティがバインドされる型を指定し `DataSource` ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5804f-136">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5804f-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="5804f-137">をホストするフォームは、 `AttributesDemoControl` ビルドするためにアセンブリへの参照を必要とし `AttributesDemoControl` ます。</span><span class="sxs-lookup"><span data-stu-id="5804f-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5804f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5804f-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5804f-139">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="5804f-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="5804f-140">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="5804f-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="5804f-141">[方法 : 標準の型のコレクションを DesignerSerializationVisibilityAttribute でシリアル化する](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="5804f-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
