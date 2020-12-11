---
title: x:Type マークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: dae1fe820b2baa32b5519b6ac8c9b103baded300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982023"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="a1f82-102">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="a1f82-102">x:Type Markup Extension</span></span>

<span data-ttu-id="a1f82-103"><xref:System.Type>指定された XAML 型の基になる型である CLR オブジェクトを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1f82-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a1f82-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="a1f82-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a1f82-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="a1f82-105">XAML Object Element Usage</span></span>

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a><span data-ttu-id="a1f82-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="a1f82-106">XAML Values</span></span>

|||
|-|-|
|`prefix`|<span data-ttu-id="a1f82-107">省略可能。</span><span class="sxs-lookup"><span data-stu-id="a1f82-107">Optional.</span></span> <span data-ttu-id="a1f82-108">既定以外の XAML 名前空間をマップするプレフィックス。</span><span class="sxs-lookup"><span data-stu-id="a1f82-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="a1f82-109">多くの場合、プレフィックスを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a1f82-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="a1f82-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1f82-110">See Remarks.</span></span>|
|`typeNameValue`|<span data-ttu-id="a1f82-111">必須。</span><span class="sxs-lookup"><span data-stu-id="a1f82-111">Required.</span></span> <span data-ttu-id="a1f82-112">現在の既定の XAML 名前空間に解決可能な型名。または、が指定されている場合は、指定されたマップされたプレフィックス `prefix` 。</span><span class="sxs-lookup"><span data-stu-id="a1f82-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a1f82-113">注釈</span><span class="sxs-lookup"><span data-stu-id="a1f82-113">Remarks</span></span>

<span data-ttu-id="a1f82-114">`x:Type`マークアップ拡張機能には、 `typeof()` C# の演算子または Microsoft Visual Basic の演算子と同様の関数があり `GetType` ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>

<span data-ttu-id="a1f82-115">`x:Type`マークアップ拡張機能は、型を受け取るプロパティに対して、文字列変換動作を提供し <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="a1f82-116">入力は XAML 型です。</span><span class="sxs-lookup"><span data-stu-id="a1f82-116">The input is a XAML type.</span></span> <span data-ttu-id="a1f82-117">入力 XAML 型と出力 CLR の関係では、 <xref:System.Type> <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlType> xaml スキーマコンテキストとコンテキストによって提供されるサービスに基づいて必要なを検索した後、出力は入力のになり <xref:System.Windows.Markup.IXamlTypeResolver> ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="a1f82-118">.NET XAML サービスでは、このマークアップ拡張機能の処理はクラスによって定義され <xref:System.Windows.Markup.TypeExtension> ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-118">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>

<span data-ttu-id="a1f82-119">特定のフレームワーク実装では、 <xref:System.Type> 値として使用される一部のプロパティは、型の名前 (型の文字列値) を直接受け入れることができ `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="a1f82-120">ただし、この動作の実装は複雑なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="a1f82-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="a1f82-121">例については、後述の「WPF の使用に関する注意事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1f82-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>

<span data-ttu-id="a1f82-122">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="a1f82-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="a1f82-123">`x:Type` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 拡張クラスの <xref:System.Windows.Markup.TypeExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="a1f82-124">CLR 型に基づく .NET XAML サービスの既定の XAML スキーマコンテキストでは、この属性の値は <xref:System.Reflection.MemberInfo.Name%2A> 目的の型の、またはその <xref:System.Reflection.MemberInfo.Name%2A> 前に既定以外の xaml 名前空間マッピングのプレフィックスが付いているを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-124">Under the default XAML schema context for .NET XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>

<span data-ttu-id="a1f82-125">`x:Type`マークアップ拡張機能は、オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="a1f82-126">この場合、 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 拡張機能を正しく初期化するには、プロパティの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1f82-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>

<span data-ttu-id="a1f82-127">`x:Type`マークアップ拡張機能は、verbose 属性としても使用できます。ただし、この使用は一般的ではありません。`<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="a1f82-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a1f82-128">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="a1f82-128">WPF Usage Notes</span></span>

### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="a1f82-129">既定の XAML 名前空間と型のマッピング</span><span class="sxs-lookup"><span data-stu-id="a1f82-129">Default XAML Namespace and Type Mapping</span></span>

<span data-ttu-id="a1f82-130">WPF プログラミングの既定の XAML 名前空間には、一般的な XAML シナリオに必要な XAML 型の大部分が含まれています。そのため、多くの場合、XAML 型の値を参照するときにプレフィックスを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="a1f82-131">カスタムアセンブリの型を参照している場合、または WPF アセンブリに存在するが、既定の XAML 名前空間にマップされていない CLR 名前空間の型を参照している場合は、プレフィックスの割り当てが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a1f82-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="a1f82-132">プレフィックス、XAML 名前空間、および CLR 名前空間のマッピングの詳細については、「 [WPF xaml の Xaml 名前空間と名前空間のマッピング](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1f82-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="a1f82-133">文字列型としての Typename をサポートする型プロパティ</span><span class="sxs-lookup"><span data-stu-id="a1f82-133">Type Properties That Support Typename-as-String</span></span>

<span data-ttu-id="a1f82-134">WPF は <xref:System.Type> 、 `x:Type` マークアップ拡張機能の使用を必要とせずに、型の一部のプロパティの値を指定できるようにする手法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a1f82-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="a1f82-135">代わりに、型に名前を付けた文字列として値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="a1f82-136">この例 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> として、とが <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType> あります。</span><span class="sxs-lookup"><span data-stu-id="a1f82-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a1f82-137">この動作のサポートは、型コンバーターまたはマークアップ拡張機能では提供されません。</span><span class="sxs-lookup"><span data-stu-id="a1f82-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="a1f82-138">代わりに、これはを介して実装される遅延動作です <xref:System.Windows.FrameworkElementFactory> 。</span><span class="sxs-lookup"><span data-stu-id="a1f82-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>

<span data-ttu-id="a1f82-139">Silverlight は同様の規則をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a1f82-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="a1f82-140">実際、Silverlight は、XAML 言語サポートでは現在サポートされておらず、 `{x:Type}` `{x:Type}` WPF-Silverlight xaml 移行をサポートするように設計されたいくつかの状況以外では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a1f82-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="a1f82-141">そのため、typename としての typename の動作は、が値であるすべての Silverlight ネイティブプロパティ評価に組み込まれてい <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>

## <a name="xaml-2009"></a><span data-ttu-id="a1f82-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="a1f82-142">XAML 2009</span></span>

<span data-ttu-id="a1f82-143">XAML 2009 は、ジェネリック型の追加サポートを提供し、 `x:TypeArguments` `x:Type` このサポートを提供するためにおよびの機能の動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="a1f82-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>

- <span data-ttu-id="a1f82-144">`x:TypeArguments` また、ジェネリックオブジェクトのインスタンス化に関連付けられたオブジェクト要素は、ルート以外の要素にもできます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="a1f82-145">詳細については、 [X:TypeArguments ディレクティブ](xtypearguments-directive.md)の「XAML 2009」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1f82-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

- <span data-ttu-id="a1f82-146">XAML 2009 では、マークアップでジェネリック型の制約を指定するための構文がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a1f82-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="a1f82-147">これは `x:TypeArguments` 、、、 `x:Type` またはの2つの機能の組み合わせによって使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>

- <span data-ttu-id="a1f82-148">XAML 2009 を読み込み用に処理するときの WPF XAML の実装では、型を使用する特定のフレームワークプロパティの暗黙的な型変換動作にもこの機能が追加され <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>

<span data-ttu-id="a1f82-149">WPF では、XAML 2009 の機能を使用できますが、ルース XAML (マークアップコンパイルされていない XAML) に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1f82-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="a1f82-150">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a1f82-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1f82-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1f82-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="a1f82-152">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a1f82-152">Styling and Templating</span></span>](../net/wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a1f82-153">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="a1f82-153">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
- [<span data-ttu-id="a1f82-154">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="a1f82-154">Markup Extensions and WPF XAML</span></span>](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
