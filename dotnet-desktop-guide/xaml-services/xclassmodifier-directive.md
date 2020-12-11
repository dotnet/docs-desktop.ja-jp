---
title: x:ClassModifier ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 2d795ad1caa766d21ea98e5a97c98304067cbef1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980188"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="fead1-102">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="fead1-102">x:ClassModifier Directive</span></span>

<span data-ttu-id="fead1-103">が指定されている場合に XAML のコンパイル動作 `x:Class` を変更します。</span><span class="sxs-lookup"><span data-stu-id="fead1-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="fead1-104">具体的には、アクセスレベル (既定値) を持つ部分を作成するのではなく、指定されたが `class` `Public` `x:Class` アクセスレベルで作成され `NotPublic` ます。</span><span class="sxs-lookup"><span data-stu-id="fead1-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="fead1-105">この動作は、生成されたアセンブリのクラスのアクセスレベルに影響します。</span><span class="sxs-lookup"><span data-stu-id="fead1-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="fead1-106">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="fead1-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="fead1-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="fead1-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="fead1-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="fead1-108">*NotPublic*</span></span>|<span data-ttu-id="fead1-109">を指定するために渡す正確な文字列は、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 使用する分離コードプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fead1-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="fead1-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fead1-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="fead1-111">依存関係</span><span class="sxs-lookup"><span data-stu-id="fead1-111">Dependencies</span></span>

<span data-ttu-id="fead1-112">[x:Class](xclass-directive.md) も同じ要素に指定する必要があり、その要素はページのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fead1-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="fead1-113">詳細については、「 [ \[ \] 4.3.1.8」セクション](/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fead1-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="fead1-114">注釈</span><span class="sxs-lookup"><span data-stu-id="fead1-114">Remarks</span></span>

<span data-ttu-id="fead1-115">`x:ClassModifier`.NET XAML サービスの使用におけるの値は、プログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fead1-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="fead1-116">使用する文字列は、各言語がを実装する方法、およびが返す型コンバーターによって異なり <xref:System.CodeDom.Compiler.CodeDomProvider> ます。これにより、との意味が定義され、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> その言語で大文字と小文字が区別されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="fead1-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="fead1-117">C# の場合、指定するために渡す文字列 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> は `internal` です。</span><span class="sxs-lookup"><span data-stu-id="fead1-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="fead1-118">Microsoft Visual Basic .NET の場合、指定するために渡す文字列 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> は `Friend` です。</span><span class="sxs-lookup"><span data-stu-id="fead1-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="fead1-119">C++/CLI では、XAML のコンパイルをサポートするターゲットは存在しません。したがって、渡す値は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="fead1-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="fead1-120">を指定することもできます <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` C# の場合は `Public` Visual Basic)。ただし、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> は、 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> が既に既定の動作であるため、を指定することはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="fead1-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="fead1-121">C# のなど、ユーザーコードのアクセスレベルの制限が同じである他の値 `private` は、XAML では入れ子になったクラス参照がサポートされていないため、には関係ありません `x:ClassModifier` 。したがって、 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 修飾子は同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fead1-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="fead1-122">セキュリティに関するメモ</span><span class="sxs-lookup"><span data-stu-id="fead1-122">Security Notes</span></span>

<span data-ttu-id="fead1-123">で宣言されているアクセスレベル `x:ClassModifier` は、特定のフレームワークとその機能によって解釈されることもあります。</span><span class="sxs-lookup"><span data-stu-id="fead1-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="fead1-124">WPF には、の型を読み込んでインスタンス化する機能が含まれてい `x:ClassModifier` `internal` ます。これは、そのクラスが、パッケージ URI 参照を通じて WPF リソースから参照されている場合です。</span><span class="sxs-lookup"><span data-stu-id="fead1-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="fead1-125">このケースの結果として、他のフレームワークによって実装されている可能性がある場合は、を排他的に使用して、 `x:ClassModifier` 可能なすべてのインスタンス化試行をブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="fead1-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="fead1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="fead1-126">See also</span></span>

- [<span data-ttu-id="fead1-127">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="fead1-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="fead1-128">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="fead1-128">Code-Behind and XAML in WPF</span></span>](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="fead1-129">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="fead1-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="fead1-130">セキュリティ (WPF)</span><span class="sxs-lookup"><span data-stu-id="fead1-130">Security (WPF)</span></span>](../framework/wpf/security-wpf.md)
- [<span data-ttu-id="fead1-131">WPF から App.xaml に移行された型</span><span class="sxs-lookup"><span data-stu-id="fead1-131">Types Migrated from WPF to System.Xaml</span></span>](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
