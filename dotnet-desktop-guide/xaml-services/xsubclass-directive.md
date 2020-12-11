---
title: x:Subclass ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: 5da3634ac05b4f6a3825dae87e361003518b0830
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985736"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="ed4d6-102">x:Subclass ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ed4d6-102">x:Subclass Directive</span></span>

<span data-ttu-id="ed4d6-103">が指定されている場合に XAML マークアップのコンパイル動作 `x:Class` を変更します。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="ed4d6-104">に基づく部分クラスを作成する代わりに、 `x:Class` 指定されたが `x:Class` 中間クラスとして作成され、指定された派生クラスがに基づいていると想定され `x:Class` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="ed4d6-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="ed4d6-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="ed4d6-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="ed4d6-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="ed4d6-107">省略可能。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-107">Optional.</span></span> <span data-ttu-id="ed4d6-108">を含む CLR 名前空間を指定し `classname` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="ed4d6-109">を指定した場合 `namespace` 、ドット (.) は `namespace` とを分離し `classname` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="ed4d6-110">必須。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-110">Required.</span></span> <span data-ttu-id="ed4d6-111">読み込まれた XAML とその XAML の分離コードを接続する部分クラスの CLR 名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="ed4d6-112">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="ed4d6-113">省略可能。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-113">Optional.</span></span> <span data-ttu-id="ed4d6-114">は `namespace` 、各名前空間が他の名前空間を解決できるかどうかとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="ed4d6-115">を含む CLR 名前空間を指定し `subclassName` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="ed4d6-116">を指定した場合 `subclassName` 、ドット (.) は `subclassNamespace` とを分離し `subclassName` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="ed4d6-117">必須。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-117">Required.</span></span> <span data-ttu-id="ed4d6-118">サブクラスの CLR 名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="ed4d6-119">依存関係</span><span class="sxs-lookup"><span data-stu-id="ed4d6-119">Dependencies</span></span>

<span data-ttu-id="ed4d6-120">[X:Class ディレクティブ](xclass-directive.md) は、同じオブジェクトでも指定する必要があります。また、そのオブジェクトは XAML 運用のルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed4d6-121">注釈</span><span class="sxs-lookup"><span data-stu-id="ed4d6-121">Remarks</span></span>

<span data-ttu-id="ed4d6-122">`x:Subclass` 使用法は、主に部分クラス宣言をサポートしない言語を対象としています。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="ed4d6-123">として使用されるクラスは、 `x:Subclass` 入れ子になったクラスにすることはできません。また、 `x:Subclass` 「依存関係」セクションで説明されているように、ルートオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="ed4d6-124">それ以外の場合、の概念上の意味 `x:Subclass` は、.NET XAML サービスの実装によって定義されていません。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="ed4d6-125">これは、.NET XAML サービスの動作では、XAML マークアップとバッキングコードの接続に使用されるプログラミングモデル全体が指定されていないためです。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="ed4d6-126">およびに関連するその他の概念の実装 `x:Class` `x:Subclass` は、プログラミングモデルまたはアプリケーションモデルを使用して、XAML マークアップ、コンパイルされたマークアップ、および CLR ベースの分離コードを接続する方法を定義する特定のフレームワークによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="ed4d6-127">各フレームワークには、動作の一部またはビルド環境に含まれる必要がある特定のコンポーネントを有効にする独自のビルドアクションがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="ed4d6-128">フレームワーク内では、ビルドアクションは、分離コードに使用される特定の CLR 言語によって異なる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="ed4d6-129">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="ed4d6-129">WPF Usage Notes</span></span>

<span data-ttu-id="ed4d6-130">`x:Subclass` は、が既に存在するアプリケーション定義内のページルートまたはルートに配置でき <xref:System.Windows.Application> `x:Class` ます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="ed4d6-131">`x:Subclass`ページまたはアプリケーションルート以外の要素での宣言、または存在しない要素の指定により `x:Class` 、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="ed4d6-132">このシナリオに対して正しく動作する派生クラスを作成するの `x:Subclass` は非常に複雑です。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="ed4d6-133">場合によっては、中間ファイル (マークアップコンパイルによってプロジェクトの obj フォルダーに生成された g ファイル) を調べて、.xaml ファイル名が含まれている名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="ed4d6-134">これらの中間ファイルを使用すると、コンパイルされたアプリケーションの部分クラスに結合されている特定のプログラミング構成要素の発生元を特定できます。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="ed4d6-135">`internal override` `Friend Overrides` コンパイル時に中間クラスで作成されたハンドラーのスタブをオーバーライドするには、派生クラスのイベントハンドラーが (Microsoft Visual Basic) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="ed4d6-136">それ以外の場合は、派生クラスの実装によって中間クラスの実装が非表示になり、中間クラスのハンドラーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="ed4d6-137">との両方を定義する場合 `x:Class` `x:Subclass` 、によって参照されるクラスの実装を指定する必要はありません `x:Class` 。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="ed4d6-138">属性を使用して名前を指定するだけで、 `x:Class` 中間ファイルに作成するクラスに関するガイダンスがコンパイラに提供されます (この場合、コンパイラは既定の名前を選択しません)。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="ed4d6-139">クラスには実装を与えることができますが `x:Class` 、これはとの両方を使用する場合の一般的なシナリオではありません `x:Class` `x:Subclass` 。</span><span class="sxs-lookup"><span data-stu-id="ed4d6-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed4d6-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed4d6-140">See also</span></span>

- [<span data-ttu-id="ed4d6-141">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ed4d6-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="ed4d6-142">WPF における XAML とカスタム クラス</span><span class="sxs-lookup"><span data-stu-id="ed4d6-142">XAML and Custom Classes for WPF</span></span>](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
