---
title: x:Member ディレクティブ
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: dc3779f05515af744db5a9c47cd56ebf1f56967a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980143"
---
# <a name="xmember-directive"></a><span data-ttu-id="525d8-102">x:Member ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="525d8-102">x:Member Directive</span></span>

<span data-ttu-id="525d8-103">マークアップで XAML メンバーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="525d8-103">Declares a XAML member in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="525d8-104">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="525d8-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="525d8-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="525d8-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="525d8-106">XAML 運用環境のバッキング クラスまたは部分クラスの名前。</span><span class="sxs-lookup"><span data-stu-id="525d8-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`memberName`|<span data-ttu-id="525d8-107">定義されるプロパティのメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="525d8-107">Member name of the property being defined.</span></span>|

## <a name="remarks"></a><span data-ttu-id="525d8-108">注釈</span><span class="sxs-lookup"><span data-stu-id="525d8-108">Remarks</span></span>

<span data-ttu-id="525d8-109">.NET XAML サービスの実装では、。</span><span class="sxs-lookup"><span data-stu-id="525d8-109">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="525d8-110">`x:Member` には直接の型のバッキングはありませんが、<xref:System.Windows.Markup.MemberDefinition> クラスによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="525d8-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="525d8-111">XAML ノード ストリームでは、`x:Member` 要素は、XAML 言語の XAML 名前空間から `Member` という名前のメンバーとして表されます。</span><span class="sxs-lookup"><span data-stu-id="525d8-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="525d8-112">メンバー `Member` は、マークアップによって宣言された属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="525d8-112">The member `Member` holds attributes as declared by markup.</span></span>

<span data-ttu-id="525d8-113">との意味 `Name` `Type` は、.Net XAML サービスレベルでは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="525d8-113">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="525d8-114">これらは、特定のフレームワークによって課される可能性がある規則の下で後に解釈される文字列の値として、初期の XAML ノード ストリームに格納されます。</span><span class="sxs-lookup"><span data-stu-id="525d8-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="525d8-115">意味は、実装によって、XAML の名前および XAML 型の意味と揃えるか、バッキング型のシステムでのみ有効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="525d8-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="525d8-116">マークアップでメンバーの定義を指定する手段として `x:Members` の実用的な使用法をサポートするため、メンバーを変更可能なクラスに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="525d8-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="525d8-117">目的とするモデルは、`x:Members` が `x:Class` を指定する型のメンバーとして存在することです。</span><span class="sxs-lookup"><span data-stu-id="525d8-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="525d8-118">ただし、型とメンバーの関連付け、または動的メンバー定義の生成のためのメカニズムは、.NET XAML サービスレベルではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="525d8-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="525d8-119">これは、XAML のメンバーの定義をサポートするアプリケーション モデルがある個々のフレームワークに残されています。</span><span class="sxs-lookup"><span data-stu-id="525d8-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="525d8-120">一般に、XAML をマークアップ コンパイルするとともに、XAML と分離コードの統合または純粋な XAML からのアセンブリの生成を行う MSBUILD のビルド操作が、この機能をサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="525d8-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="525d8-121">Windows Workflow Foundation の x:Property</span><span class="sxs-lookup"><span data-stu-id="525d8-121">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="525d8-122">Windows Workflow Foundation では、 `x:Property` は、全体が XAML で構成されるカスタム アクティビティのメンバーや、分離コードを含むアクティビティ デザイナーの XAML で定義された動的メンバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="525d8-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="525d8-123">`x:Class` は、XAML の運用環境のルート要素にも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="525d8-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="525d8-124">これは、.NET XAML サービスレベルでは必須ではありませんが、カスタムアクティビティをサポートし、XAML を Windows Workflow Foundation XAML のビルドアクションによって XAML の実稼働が読み込まれる場合の要件になります。</span><span class="sxs-lookup"><span data-stu-id="525d8-124">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="525d8-125">Windows Workflow Foundation は、属性の意図された値として純粋な XAML 型名を使用しません `x:Property` `Type` 。代わりに、ここに記載されていない規則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="525d8-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="525d8-126">詳細については、「 [DynamicActivity の作成](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="525d8-126">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
