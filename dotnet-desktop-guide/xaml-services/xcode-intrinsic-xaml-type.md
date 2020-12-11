---
title: 'x:Code 組み込み XAML 型 '
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 1e44ac3fec76ef6f5041d712110ff40c2ec3de03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980164"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="a2278-102">x:Code 組み込み XAML 型 </span><span class="sxs-lookup"><span data-stu-id="a2278-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="a2278-103">XAML の実稼働環境内でのコードの配置を許可します。</span><span class="sxs-lookup"><span data-stu-id="a2278-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="a2278-104">このようなコードは、xaml をコンパイルする任意の XAML プロセッサの実装によってコンパイルすることも、ランタイムによる解釈など、後で使用できるように XAML の運用環境でコンパイルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a2278-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a2278-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="a2278-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="a2278-106">注釈</span><span class="sxs-lookup"><span data-stu-id="a2278-106">Remarks</span></span>

<span data-ttu-id="a2278-107">`x:Code`Xaml ディレクティブ要素内のコードは、通常の XML 名前空間と、指定された xaml 名前空間内で引き続き解釈されます。</span><span class="sxs-lookup"><span data-stu-id="a2278-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="a2278-108">そのため、通常はセグメント内で使用されるコードを囲む必要が `x:Code` `CDATA` あります。</span><span class="sxs-lookup"><span data-stu-id="a2278-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="a2278-109">`x:Code` は、XAML 運用環境のすべての配置メカニズムで許可されていません。</span><span class="sxs-lookup"><span data-stu-id="a2278-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="a2278-110">特定のフレームワーク (WPF など) では、コードをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="a2278-111">他のフレームワークでは、 `x:Code` 一般に使用が禁止されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="a2278-112">マネージコンテンツを許可するフレームワークの場合 `x:Code` 、コンテンツに使用する正しい言語コンパイラは、 `x:Code` アプリケーションのコンパイルに使用される、含んでいるプロジェクトの設定とターゲットによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a2278-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a2278-113">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="a2278-113">WPF Usage Notes</span></span>

<span data-ttu-id="a2278-114">WPF で宣言され `x:Code` たコードには、いくつかの注目すべき制限があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="a2278-115">`x:Code`ディレクティブ要素は、XAML 運用のルート要素の直接の子要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="a2278-116">[X:Class ディレクティブ](xclass-directive.md) は、親ルート要素で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="a2278-117">内に配置されたコードは、 `x:Code` その XAML ページ用に既に作成されている部分クラスのスコープ内になるように、コンパイルによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="a2278-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="a2278-118">したがって、定義するすべてのコードは、その部分クラスのメンバーまたは変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="a2278-119">クラスを部分クラス内に入れ子にする以外に、追加のクラスを定義することはできません (入れ子にすることはできますが、入れ子になったクラスは XAML で参照できないため、一般的ではありません)。</span><span class="sxs-lookup"><span data-stu-id="a2278-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="a2278-120">既存の部分クラスに使用されている名前空間以外の CLR 名前空間を定義したり、に追加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a2278-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="a2278-121">部分クラスの CLR 名前空間の外部にあるコードエンティティへの参照はすべて、完全修飾されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="a2278-122">宣言されるメンバーが部分クラスのオーバーライド可能なメンバーをオーバーライドする場合は、言語固有の override キーワードを使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2278-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="a2278-123">スコープ内で宣言 `x:Code` されたメンバーが xaml から作成された部分クラスのメンバーと競合する場合、コンパイラが競合を報告する方法では、xaml ファイルをコンパイルまたは読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="a2278-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2278-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2278-124">See also</span></span>

- [<span data-ttu-id="a2278-125">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="a2278-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="a2278-126">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="a2278-126">Code-Behind and XAML in WPF</span></span>](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="a2278-127">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="a2278-127">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
