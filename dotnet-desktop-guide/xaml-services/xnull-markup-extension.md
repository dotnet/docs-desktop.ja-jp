---
title: x:Null のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7f7c4cd44448b6e4e8b8934a63b56b910ce0428a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980101"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="49827-102">x:Null のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="49827-102">x:Null Markup Extension</span></span>

<span data-ttu-id="49827-103">`null`XAML メンバーの値としてを指定します。</span><span class="sxs-lookup"><span data-stu-id="49827-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="49827-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="49827-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="49827-105">注釈</span><span class="sxs-lookup"><span data-stu-id="49827-105">Remarks</span></span>

<span data-ttu-id="49827-106">C# および C++ での null 参照のキーワードが null です。</span><span class="sxs-lookup"><span data-stu-id="49827-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="49827-107">Null 参照の Microsoft Visual Basic キーワードはです `Nothing` が、 `{x:Null}` xaml に関連付けた分離コード言語に関係なく、常に xaml の使用法としてを使用します。</span><span class="sxs-lookup"><span data-stu-id="49827-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="49827-108">`x:Null`マークアップ拡張機能には、設定可能なプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="49827-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="49827-109">Null 使用は、多くの場合、CLR 値の XAML メンバー公開に関連付けられてい <xref:System.Nullable%601> ます。</span><span class="sxs-lookup"><span data-stu-id="49827-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="49827-110">`x:Null`マークアップ拡張機能は、すべての XAML マークアップ拡張機能と同様に、中かっこ () を使用して、 `{,}` リテラルまたはイベントハンドラー参照以外の属性値の処理をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="49827-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="49827-111">属性構文は、このマークアップ拡張機能で最も頻繁に使用される構文です。</span><span class="sxs-lookup"><span data-stu-id="49827-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="49827-112">オブジェクト要素の構文は `<x:Null />` 技術的には可能ですが、 `x:Null` マークアップ拡張機能に位置指定パラメーターも構築引数もないため、ほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="49827-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="49827-113">マークアップ拡張機能の詳細については、「 [マークアップ拡張機能と WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49827-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="49827-114">.NET XAML サービスでは、このマークアップ拡張機能の処理はクラスによって定義され <xref:System.Windows.Markup.NullExtension> ます。</span><span class="sxs-lookup"><span data-stu-id="49827-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="49827-115">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="49827-115">WPF Usage Notes</span></span>

<span data-ttu-id="49827-116">`null`は必ずしも参照型の依存関係プロパティの最初の未設定値ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="49827-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="49827-117">初期の既定値は、依存関係プロパティごとに異なる場合があり、プロパティ固有のメタデータに基づいている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="49827-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="49827-118">多くの依存関係プロパティは、 `null` 検証コールバックの実装により、マークアップまたはコードによって値として受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="49827-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="49827-119">依存関係プロパティの詳細については、「[依存関係プロパティの概要](../framework/wpf/advanced/dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49827-119">For more information about dependency properties, see [Dependency Properties Overview](../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49827-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="49827-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="49827-121">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="49827-121">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
- [<span data-ttu-id="49827-122">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="49827-122">Markup Extensions and WPF XAML</span></span>](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
