---
title: XAML のジェネリック
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985747"
---
# <a name="generics-in-xaml"></a><span data-ttu-id="ef285-102">XAML のジェネリック</span><span class="sxs-lookup"><span data-stu-id="ef285-102">Generics in XAML</span></span>

<span data-ttu-id="ef285-103">に実装されている .NET XAML サービスで <xref:System.Xaml?displayProperty=fullName> は、ジェネリック CLR 型の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ef285-103">.NET XAML Services as implemented in <xref:System.Xaml?displayProperty=fullName> provides support for using generic CLR types.</span></span> <span data-ttu-id="ef285-104">このサポートには、ジェネリックの制約を型引数として指定し、 `Add` ジェネリックコレクションケースに対して適切なメソッドを呼び出すことによって制約を適用する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef285-104">This support includes specifying the constraints of generics as a type argument and enforcing the constraint by calling the appropriate `Add` method for generic collection cases.</span></span> <span data-ttu-id="ef285-105">このトピックでは、XAML でのジェネリック型の使用と参照の側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef285-105">This topic describes aspects of using and referencing generic types in XAML.</span></span>

## <a name="xtypearguments"></a><span data-ttu-id="ef285-106">x:TypeArguments</span><span class="sxs-lookup"><span data-stu-id="ef285-106">x:TypeArguments</span></span>

<span data-ttu-id="ef285-107">`x:TypeArguments` は、XAML 言語で定義されたディレクティブです。</span><span class="sxs-lookup"><span data-stu-id="ef285-107">`x:TypeArguments` is a directive defined by the XAML language.</span></span> <span data-ttu-id="ef285-108">ジェネリック型によってサポートされる XAML 型のメンバーとして使用されている場合、は、 `x:TypeArguments` ジェネリックの制約型引数をバッキングコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="ef285-108">When it is used as a member of a XAML type that is backed by a generic type, `x:TypeArguments` passes constraining type arguments of the generic to the backing constructor.</span></span> <span data-ttu-id="ef285-109">.NET XAML サービスに関連する参照構文の例については、 `x:TypeArguments` 「 [x:TypeArguments ディレクティブ](xtypearguments-directive.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef285-109">For reference syntax that pertains to .NET XAML Services use of `x:TypeArguments`, which includes syntax examples, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

<span data-ttu-id="ef285-110">は文字列を受け取り、型コンバーターを使用しているため `x:TypeArguments` 、通常は属性として XAML の使用法で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="ef285-110">Because `x:TypeArguments` takes a string, and has type converter backing, it is typically declared in XAML usage as an attribute.</span></span>

<span data-ttu-id="ef285-111">XAML ノードストリームでは、によって宣言された情報は、 `x:TypeArguments` <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> `StartObject` ノードストリーム内の位置から取得できます。</span><span class="sxs-lookup"><span data-stu-id="ef285-111">In the XAML node stream, the information declared by `x:TypeArguments` can be obtained from <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> at a `StartObject` position in the node stream.</span></span> <span data-ttu-id="ef285-112">の戻り値 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> は、値のリストです <xref:System.Xaml.XamlType> 。</span><span class="sxs-lookup"><span data-stu-id="ef285-112">The return value of <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> is a list of <xref:System.Xaml.XamlType> values.</span></span> <span data-ttu-id="ef285-113">XAML 型がジェネリック型を表すかどうかの判断は、を呼び出すことによって行うことができ <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="ef285-113">Determination of whether a XAML type represents a generic type can be made by calling <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.</span></span>

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a><span data-ttu-id="ef285-114">XAML のジェネリックの規則と構文規則</span><span class="sxs-lookup"><span data-stu-id="ef285-114">Rules and Syntax Conventions for Generics in XAML</span></span>

<span data-ttu-id="ef285-115">XAML では、ジェネリック型は常に制約付きジェネリックとして表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef285-115">In XAML, a generic type must always be represented as a constrained generic.</span></span> <span data-ttu-id="ef285-116">制約のないジェネリックは、XAML 型システムまたは XAML ノードストリームには存在せず、XAML マークアップでは表現できません。</span><span class="sxs-lookup"><span data-stu-id="ef285-116">An unconstrained generic is never present in the XAML type system or a XAML node stream and cannot be represented in XAML markup.</span></span> <span data-ttu-id="ef285-117">ジェネリックは、によって参照されているジェネリックの入れ子にされた型制約である場合 `x:TypeArguments` 、またはが `x:Type` ジェネリック型の CLR 型参照を提供する場合に、XAML 属性構文内で参照できます。</span><span class="sxs-lookup"><span data-stu-id="ef285-117">A generic can be referenced within XAML attribute syntax for cases where it is a nested type constraint of a generic being referenced by `x:TypeArguments`, or for cases where `x:Type` supplies a CLR type reference for a generic type.</span></span> <span data-ttu-id="ef285-118">ジェネリックの参照は、 <xref:System.Xaml.Schema.XamlTypeTypeConverter> .NET XAML サービスによって定義されたクラスによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef285-118">Referencing generics is supported through the <xref:System.Xaml.Schema.XamlTypeTypeConverter> class defined by .NET XAML Services.</span></span>

<span data-ttu-id="ef285-119">によって有効にされる XAML 属性構文形式では、 <xref:System.Xaml.Schema.XamlTypeTypeConverter> ジェネリックの型や制約に山かっこを使用する一般的な MSIL/CLR 構文規則が変更され、代わりに制約コンテナーに対してかっこが代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef285-119">The XAML attribute syntax form enabled by <xref:System.Xaml.Schema.XamlTypeTypeConverter> alters the typical MSIL / CLR syntax convention that uses angle brackets for types and constraints of generics, and instead substitutes parentheses for the constraint container.</span></span> <span data-ttu-id="ef285-120">例については、「 [X:TypeArguments ディレクティブ](xtypearguments-directive.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef285-120">For an example, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

## <a name="generics-and-xaml-2009-features"></a><span data-ttu-id="ef285-121">ジェネリックおよび XAML 2009 の機能</span><span class="sxs-lookup"><span data-stu-id="ef285-121">Generics and XAML 2009 Features</span></span>

<span data-ttu-id="ef285-122">CLR 基本型をマップして共通言語プリミティブの XAML 型を取得するのではなく、XAML 2009 を使用する場合は、の情報項目として [xaml 2009 組み込み型](types-for-primitives.md) を使用でき `x:TypeArguments` ます。</span><span class="sxs-lookup"><span data-stu-id="ef285-122">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [XAML 2009 built-in types](types-for-primitives.md) as information items in `x:TypeArguments`.</span></span> <span data-ttu-id="ef285-123">たとえば、次のように宣言することができます (このプレフィックスは表示されませんが、xaml `x` 言語の xaml 名前空間は xaml 2009)。</span><span class="sxs-lookup"><span data-stu-id="ef285-123">For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a><span data-ttu-id="ef285-124">WPF でのジェネリックのサポート</span><span class="sxs-lookup"><span data-stu-id="ef285-124">Generics Support in WPF</span></span>

<span data-ttu-id="ef285-125">WPF を特に対象とする XAML 2006 の使用については、 [x:Class](xclass-directive.md) もと同じ要素に指定する必要があり、 `x:TypeArguments` その要素は xaml ドキュメントのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef285-125">For XAML 2006 usage when specifically targeting WPF, [x:Class](xclass-directive.md) must also be provided on the same element as `x:TypeArguments`, and that element must be the root element in a XAML document.</span></span> <span data-ttu-id="ef285-126">ルート要素は、少なくとも1つの型引数を持つジェネリック型にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef285-126">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="ef285-127">たとえば <xref:System.Windows.Navigation.PageFunction%601> です。</span><span class="sxs-lookup"><span data-stu-id="ef285-127">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

<span data-ttu-id="ef285-128">一般的な使用法をサポートするための回避策として、ジェネリック型を返すことができるカスタムマークアップ拡張機能の定義や、ジェネリック型から派生し、独自のクラス定義でジェネリック制約を平坦化するラップクラス定義の指定などがあります。</span><span class="sxs-lookup"><span data-stu-id="ef285-128">Possible workarounds to support generic usages include defining a custom markup extension that can return generic types, or providing a wrapping class definition that derives from a generic type but flattens the generic constraint in its own class definition.</span></span>

<span data-ttu-id="ef285-129">WPF では、XAML 2009 の機能をと共に使用でき `x:TypeArguments` ますが、ルース xaml (マークアップコンパイルされていない xaml) に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef285-129">In WPF you can use XAML 2009 features together with `x:TypeArguments`, but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="ef285-130">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ef285-130">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="ef285-131">.NET Framework 3.5 の Windows Workflow Foundation のカスタムワークフローでは、一般的な XAML 使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ef285-131">Custom workflows in Windows Workflow Foundation for .NET Framework 3.5 do not support generic XAML usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef285-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef285-132">See also</span></span>

- [<span data-ttu-id="ef285-133">x:TypeArguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ef285-133">x:TypeArguments Directive</span></span>](xtypearguments-directive.md)
- [<span data-ttu-id="ef285-134">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ef285-134">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="ef285-135">共通の XAML 言語プリミティブの組み込み型</span><span class="sxs-lookup"><span data-stu-id="ef285-135">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
