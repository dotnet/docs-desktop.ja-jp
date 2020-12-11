---
title: カスタム型およびライブラリの XAML 関連の CLR 属性
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 509a4b638cf8df2974f1c08309faac25c2ba8c14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985760"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a><span data-ttu-id="dd793-102">カスタム型およびライブラリの XAML 関連の CLR 属性</span><span class="sxs-lookup"><span data-stu-id="dd793-102">XAML-related CLR attributes for custom types and libraries</span></span>

<span data-ttu-id="dd793-103">このトピックでは、.NET XAML サービスによって定義される共通言語ランタイム (CLR) の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd793-103">This topic describes the common language runtime (CLR) attributes that are defined by .NET XAML Services.</span></span> <span data-ttu-id="dd793-104">また、.NET で定義されている他の CLR 属性についても説明します。この属性には、アプリケーションからアセンブリまたは型への XAML 関連のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="dd793-104">It also describes other CLR attributes that are defined in .NET that have a XAML-related scenario for application to assemblies or types.</span></span> <span data-ttu-id="dd793-105">これらの CLR 属性を持つ属性アセンブリ、型、またはメンバーは、型に関連する XAML 型システム情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dd793-105">Attributing assemblies, types, or members with these CLR attributes provides XAML type system information related to your types.</span></span> <span data-ttu-id="dd793-106">Xaml ノードストリームを直接処理するために、または専用の XAML リーダーと XAML ライターを使用して、.NET XAML サービスを使用するすべての XAML コンシューマーに情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-106">Information is provided to any XAML consumer that uses .NET XAML Services for processing the XAML node stream directly or through the dedicated XAML readers and XAML writers.</span></span>

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a><span data-ttu-id="dd793-107">カスタム型およびカスタムメンバーの CLR 属性の XAML-Related</span><span class="sxs-lookup"><span data-stu-id="dd793-107">XAML-Related CLR Attributes for Custom Types and Custom Members</span></span>

<span data-ttu-id="dd793-108">CLR 属性を使用する場合は、CLR 全体を使用して型を定義する必要があります。そうしないと、このような属性は使用できません。</span><span class="sxs-lookup"><span data-stu-id="dd793-108">Using CLR attributes entails that you are using the overall CLR to define your types, otherwise such attributes are not available.</span></span> <span data-ttu-id="dd793-109">CLR を使用して型のバッキングを定義する場合、.NET XAML サービスの XAML ライターによって使用される既定の XAML スキーマコンテキストは、バッキングアセンブリに対するリフレクションを通じて CLR の属性を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="dd793-109">If you use the CLR to define type backing, then the default XAML schema context used by .NET XAML Services XAML writers can read CLR attribution through reflection against backing assemblies.</span></span>

<span data-ttu-id="dd793-110">以下のセクションでは、カスタム型またはカスタムメンバーに適用できる XAML 関連の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd793-110">The following sections describe the XAML-related attributes that you can apply to custom types or custom members.</span></span> <span data-ttu-id="dd793-111">各 CLR 属性は、XAML 型システムに関連する情報を伝達します。</span><span class="sxs-lookup"><span data-stu-id="dd793-111">Each CLR attribute communicates information that is relevant to a XAML type system.</span></span> <span data-ttu-id="dd793-112">読み込みパスでは、属性付き情報は、XAML リーダーが有効な XAML ノードストリームを形成するのに役立ちます。また、XAML ライターが有効なオブジェクトグラフを生成するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd793-112">In the load path, the attributed information either helps the XAML reader form a valid XAML node stream, or it helps the XAML writer produce a valid object graph.</span></span> <span data-ttu-id="dd793-113">保存パスでは、属性付きの情報により、xaml リーダーは xaml 型システム情報を再構成有効な XAML ノードストリームにすることができます。または、XAML ライターまたは他の XAML コンシューマーのシリアル化ヒントまたは要件を宣言します。</span><span class="sxs-lookup"><span data-stu-id="dd793-113">In the save path, the attributed information either helps the XAML reader form a valid XAML node stream that reconstitutes XAML type system information; or it declares serialization hints or requirements for the XAML writer or other XAML consumers.</span></span>

### <a name="ambientattribute"></a><span data-ttu-id="dd793-114">AmbientAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-114">AmbientAttribute</span></span>

<span data-ttu-id="dd793-115">**リファレンスドキュメント:**<xref:System.Windows.Markup.AmbientAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-115">**Reference Documentation:** <xref:System.Windows.Markup.AmbientAttribute></span></span>

<span data-ttu-id="dd793-116">**適用対象:** アタッチ可能なプロパティをサポートするクラス、プロパティ、または `get` アクセサーのメンバー。</span><span class="sxs-lookup"><span data-stu-id="dd793-116">**Applies to:** Class, property, or `get` accessor members that support attachable properties.</span></span>

<span data-ttu-id="dd793-117">**引数:** 存在</span><span class="sxs-lookup"><span data-stu-id="dd793-117">**Arguments:** None</span></span>

<span data-ttu-id="dd793-118"><xref:System.Windows.Markup.AmbientAttribute> プロパティ、または属性付きの型を受け取るすべてのプロパティを、XAML のアンビエントプロパティの概念で解釈する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="dd793-118"><xref:System.Windows.Markup.AmbientAttribute> indicates that the property, or all properties that take the attributed type, should be interpreted under the ambient property concept in XAML.</span></span> <span data-ttu-id="dd793-119">アンビエントの概念は XAML プロセッサがメンバーの型の所有者を確認する方法と関連します。</span><span class="sxs-lookup"><span data-stu-id="dd793-119">The ambient concept relates to how XAML processors determine type owners of members.</span></span> <span data-ttu-id="dd793-120">アンビエントプロパティは、オブジェクトグラフを作成するときにパーサーコンテキストで値を使用できることが期待されるプロパティですが、すぐに作成される XAML ノードセットに対して一般的な型メンバーの参照は中断されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-120">An ambient property is a property where the value is expected to be available in the parser context when creating an object graph, but where typical type-member lookup is suspended for the immediate XAML node set being created.</span></span>

<span data-ttu-id="dd793-121">アンビエント概念はアタッチ可能なメンバーに適用できますが、CLR の属性で定義される方法の観点からはプロパティとしては表されません <xref:System.AttributeTargets> 。</span><span class="sxs-lookup"><span data-stu-id="dd793-121">The ambient concept can be applied to attachable members, which are not represented as properties in terms of how CLR attribution defines <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="dd793-122">メソッド属性の使用法は、 `get` XAML のアタッチ可能な使用をサポートするアクセサーに対してのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-122">The method attribution usage should be applied only for a `get` accessor that supports attachable usage for XAML.</span></span>

### <a name="constructorargumentattribute"></a><span data-ttu-id="dd793-123">ConstructorArgumentAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-123">ConstructorArgumentAttribute</span></span>

<span data-ttu-id="dd793-124">**リファレンスドキュメント:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-124">**Reference Documentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span></span>

<span data-ttu-id="dd793-125">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-125">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-126">**引数:** 単一のコンストラクター引数に一致するプロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-126">**Arguments:** A string that specifies the name of the property that matches a single constructor argument.</span></span>

<span data-ttu-id="dd793-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> パラメーターなしのコンストラクター構文を使用してオブジェクトを初期化できること、および指定された名前のプロパティが構築情報を提供することを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> specifies that an object can be initialized by using a non-parameterless constructor syntax, and that a property of the specified name supplies construction information.</span></span> <span data-ttu-id="dd793-128">この情報は主に XAML シリアル化用です。</span><span class="sxs-lookup"><span data-stu-id="dd793-128">This information is primarily for XAML serialization.</span></span> <span data-ttu-id="dd793-129">詳細については、「<xref:System.Windows.Markup.ConstructorArgumentAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd793-129">For more information, see <xref:System.Windows.Markup.ConstructorArgumentAttribute>.</span></span>

### <a name="contentpropertyattribute"></a><span data-ttu-id="dd793-130">ContentPropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-130">ContentPropertyAttribute</span></span>

<span data-ttu-id="dd793-131">**リファレンスドキュメント:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-131">**Reference Documentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span></span>

<span data-ttu-id="dd793-132">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-132">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-133">**引数:** 属性付きの型のメンバーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-133">**Arguments:** A string that specifies the name of a member of the attributed type.</span></span>

<span data-ttu-id="dd793-134"><xref:System.Windows.Markup.ContentPropertyAttribute> 引数によって指定されるプロパティが、その型の XAML コンテンツプロパティとして機能する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="dd793-134"><xref:System.Windows.Markup.ContentPropertyAttribute> indicates that the property as named by the argument should serve as the XAML content property for that type.</span></span> <span data-ttu-id="dd793-135">XAML コンテンツプロパティの定義は、定義する型に割り当てることができるすべての派生型に継承されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-135">The XAML content property definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="dd793-136">特定の派生型に対してを適用することで、特定の派生型の定義をオーバーライドでき <xref:System.Windows.Markup.ContentPropertyAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-136">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.ContentPropertyAttribute> on the specific derived type.</span></span>

<span data-ttu-id="dd793-137">XAML コンテンツプロパティとして機能するプロパティでは、プロパティのプロパティ要素のタグ付けを XAML の使用時に省略できます。</span><span class="sxs-lookup"><span data-stu-id="dd793-137">For the property that serves as the XAML content property, property element tagging for the property can be omitted in the XAML usage.</span></span> <span data-ttu-id="dd793-138">通常、コンテンツモデルとコンテインメントモデルの簡素化された XAML マークアップを促進する XAML コンテンツプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-138">Typically, you designate XAML content properties that promote a streamlined XAML markup for your content and containment models.</span></span> <span data-ttu-id="dd793-139">XAML コンテンツプロパティとして指定できるのは1つのメンバーだけなので、XAML コンテンツプロパティとして指定する必要がある型のいくつかのコンテナープロパティについて、設計上の選択肢がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-139">Because only one member can be designated as the XAML content property, you sometimes have design choices to make regarding which of several container properties of a type should be designated as the XAML content property.</span></span> <span data-ttu-id="dd793-140">その他のコンテナープロパティは、明示的なプロパティ要素と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-140">The other container properties must be used with explicit property elements.</span></span>

<span data-ttu-id="dd793-141">XAML ノードストリームでは、XAML コンテンツプロパティは `StartMember` 、の `EndMember` プロパティの名前を使用して、およびノードを生成し <xref:System.Xaml.XamlMember> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-141">In the XAML node stream, XAML content properties still produce `StartMember` and `EndMember` nodes, using the name of the property for the <xref:System.Xaml.XamlMember>.</span></span> <span data-ttu-id="dd793-142">メンバーが XAML コンテンツプロパティであるかどうかを判断するには、 <xref:System.Xaml.XamlType> 位置から値を調べ、 `StartObject` の値を取得し <xref:System.Xaml.XamlType.ContentProperty%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-142">To determine whether a member is the XAML content property, examine the <xref:System.Xaml.XamlType> value from the `StartObject` position and obtain the value of <xref:System.Xaml.XamlType.ContentProperty%2A>.</span></span>

### <a name="contentwrapperattribute"></a><span data-ttu-id="dd793-143">ContentWrapperAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-143">ContentWrapperAttribute</span></span>

<span data-ttu-id="dd793-144">**リファレンスドキュメント:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-144">**Reference Documentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span></span>

<span data-ttu-id="dd793-145">**適用対象:** クラス、特にコレクション型。</span><span class="sxs-lookup"><span data-stu-id="dd793-145">**Applies to:** Class, specifically collection types.</span></span>

<span data-ttu-id="dd793-146">**引数:**<xref:System.Type>外部コンテンツのコンテンツラッパーの種類として使用する型を指定する。</span><span class="sxs-lookup"><span data-stu-id="dd793-146">**Arguments:** A <xref:System.Type> that specifies the type to use as the content wrapper type for foreign content.</span></span>

<span data-ttu-id="dd793-147"><xref:System.Windows.Markup.ContentWrapperAttribute> 外部コンテンツをラップするために使用される、関連付けられたコレクション型の1つ以上の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-147"><xref:System.Windows.Markup.ContentWrapperAttribute> specifies one or more types on the associated collection type that will be used to wrap foreign content.</span></span> <span data-ttu-id="dd793-148">外部コンテンツとは、コンテンツプロパティの型の型システム制約が、所有する型の XAML の使用によってサポートされる可能性のあるすべてのコンテンツケースをキャプチャしない場合を指します。</span><span class="sxs-lookup"><span data-stu-id="dd793-148">Foreign content refers to cases where the type system constraints on the type of the content property do not capture all of the possible content cases that XAML usage for the owning type would support.</span></span> <span data-ttu-id="dd793-149">たとえば、特定の型のコンテンツに対する XAML サポートは、厳密に型指定されたジェネリックの文字列をサポートする場合があり <xref:System.Collections.ObjectModel.Collection%601> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-149">For example, XAML support for content of a particular type might support strings in a strongly typed generic <xref:System.Collections.ObjectModel.Collection%601>.</span></span> <span data-ttu-id="dd793-150">コンテンツラッパーは、既存のマークアップ規則を、テキスト関連のコンテンツモデルの移行など、コレクションの割り当て可能な値の XAML の構想に移行する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dd793-150">Content wrappers are useful for migrating pre-existing markup conventions into XAML's conception of assignable values for collections, such as migrating text-related content models.</span></span>

<span data-ttu-id="dd793-151">複数のコンテンツラッパーの種類を指定するには、属性を複数回適用します。</span><span class="sxs-lookup"><span data-stu-id="dd793-151">To specify more than one content wrapper type, apply the attribute multiple times.</span></span>

### <a name="dependsonattribute"></a><span data-ttu-id="dd793-152">依存関係の Sonattribute</span><span class="sxs-lookup"><span data-stu-id="dd793-152">DependsOnAttribute</span></span>

<span data-ttu-id="dd793-153">**リファレンスドキュメント:**  <xref:System.Windows.Markup.DependsOnAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-153">**Reference Documentation:**  <xref:System.Windows.Markup.DependsOnAttribute></span></span>

<span data-ttu-id="dd793-154">**適用対象:** "</span><span class="sxs-lookup"><span data-stu-id="dd793-154">**Applies to:** Property</span></span>

<span data-ttu-id="dd793-155">**引数:** 属性付きの型の別のメンバーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-155">**Arguments:** A string that specifies the name of another member of the attributed type.</span></span>

<span data-ttu-id="dd793-156"><xref:System.Windows.Markup.DependsOnAttribute> 属性付きプロパティが別のプロパティの値に依存していることを示します。</span><span class="sxs-lookup"><span data-stu-id="dd793-156"><xref:System.Windows.Markup.DependsOnAttribute> indicates that the attributed property depends on the value of another property.</span></span> <span data-ttu-id="dd793-157">この属性をプロパティ定義に適用すると、XAML オブジェクトの書き込み時に依存プロパティが最初に処理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd793-157">Applying this attribute to a property definition ensures that the dependent properties are processed first in XAML object writing.</span></span> <span data-ttu-id="dd793-158">の使用法では <xref:System.Windows.Markup.DependsOnAttribute> 、特定の解析順序を有効なオブジェクト作成のために従う必要がある型のプロパティの例外的なケースを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-158">Usages of <xref:System.Windows.Markup.DependsOnAttribute> specify the exceptional cases of properties on types where a specific order of parsing must be followed for valid object creation.</span></span>

<span data-ttu-id="dd793-159">複数 <xref:System.Windows.Markup.DependsOnAttribute> のケースをプロパティ定義に適用できます。</span><span class="sxs-lookup"><span data-stu-id="dd793-159">You can apply multiple <xref:System.Windows.Markup.DependsOnAttribute> cases to a property definition.</span></span>

### <a name="markupextensionreturntypeattribute"></a><span data-ttu-id="dd793-160">MarkupExtensionReturnTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-160">MarkupExtensionReturnTypeAttribute</span></span>

<span data-ttu-id="dd793-161">**リファレンスドキュメント:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-161">**Reference Documentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span></span>

<span data-ttu-id="dd793-162">**適用対象:** クラス。派生型であることが想定されて <xref:System.Windows.Markup.MarkupExtension> います。</span><span class="sxs-lookup"><span data-stu-id="dd793-162">**Applies to:** Class, which is expected to be a <xref:System.Windows.Markup.MarkupExtension> derived type.</span></span>

<span data-ttu-id="dd793-163">**引数:**<xref:System.Type> `ProvideValue` 属性付きの結果として予想される最も正確な型を指定する <xref:System.Windows.Markup.MarkupExtension> 。</span><span class="sxs-lookup"><span data-stu-id="dd793-163">**Arguments:** A <xref:System.Type> that specifies the most precise type to expect as the `ProvideValue` result of the attributed <xref:System.Windows.Markup.MarkupExtension>.</span></span>

<span data-ttu-id="dd793-164">詳細については、「 [XAML のマークアップ拡張機能の概要](markup-extensions-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd793-164">For more information, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

### <a name="namescopepropertyattribute"></a><span data-ttu-id="dd793-165">NameScopePropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-165">NameScopePropertyAttribute</span></span>

<span data-ttu-id="dd793-166">**リファレンスドキュメント:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-166">**Reference Documentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span></span>

<span data-ttu-id="dd793-167">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-167">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-168">**引数:** は、次の2つの形式の属性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="dd793-168">**Arguments:** Supports two forms of attribution:</span></span>

- <span data-ttu-id="dd793-169">属性付きの型のプロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-169">A string that specifies the name of a property on the attributed type.</span></span>

- <span data-ttu-id="dd793-170">プロパティの名前、および <xref:System.Type> 名前付きプロパティを定義する型のを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-170">A string that specifies the name of a property, and a <xref:System.Type> for the type that defines the named property.</span></span> <span data-ttu-id="dd793-171">この形式は、アタッチ可能なメンバーを XAML 名前スコーププロパティとして指定するためのものです。</span><span class="sxs-lookup"><span data-stu-id="dd793-171">This form is for specifying an attachable member as the XAML namescope property.</span></span>

<span data-ttu-id="dd793-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> 属性付きクラスの XAML 名前スコープの値を提供するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> specifies a property that provides the XAML namescope value for the attributed class.</span></span> <span data-ttu-id="dd793-173">XAML 名前スコーププロパティは、 <xref:System.Windows.Markup.INameScope> 実際の xaml 名前スコープ、ストア、およびその動作を実装して保持するオブジェクトを参照することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="dd793-173">The XAML namescope property is expected to reference an object that implements <xref:System.Windows.Markup.INameScope> and holds the actual XAML namescope, its store, and its behavior.</span></span>

### <a name="runtimenamepropertyattribute"></a><span data-ttu-id="dd793-174">RuntimeNamePropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-174">RuntimeNamePropertyAttribute</span></span>

<span data-ttu-id="dd793-175">**リファレンスドキュメント:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-175">**Reference Documentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span></span>

<span data-ttu-id="dd793-176">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-176">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-177">**引数:** 属性付きの型の実行時の名前プロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-177">**Arguments:** A string that specifies the name of the run-time name property on the attributed type.</span></span>

<span data-ttu-id="dd793-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> XAML [X:Name ディレクティブ](xname-directive.md)にマップされる属性付きの型のプロパティを報告します。</span><span class="sxs-lookup"><span data-stu-id="dd793-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> reports a property of the attributed type that maps to the XAML [x:Name Directive](xname-directive.md).</span></span> <span data-ttu-id="dd793-179">プロパティは型である必要があり、 <xref:System.String> 読み取り/書き込み可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-179">The property must be of type <xref:System.String> and must be read/write.</span></span>

<span data-ttu-id="dd793-180">定義は、定義する型に割り当て可能なすべての派生型に継承されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-180">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="dd793-181">特定の派生型に対してを適用することで、特定の派生型の定義をオーバーライドでき <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-181">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> on the specific derived type.</span></span>

### <a name="trimsurroundingwhitespaceattribute"></a><span data-ttu-id="dd793-182">TrimSurroundingWhitespaceAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-182">TrimSurroundingWhitespaceAttribute</span></span>

<span data-ttu-id="dd793-183">**リファレンスドキュメント:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-183">**Reference Documentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span></span>

<span data-ttu-id="dd793-184">**適用対象:** な</span><span class="sxs-lookup"><span data-stu-id="dd793-184">**Applies to:** Types</span></span>

<span data-ttu-id="dd793-185">**引数:** 存在.</span><span class="sxs-lookup"><span data-stu-id="dd793-185">**Arguments:** None.</span></span>

<span data-ttu-id="dd793-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> は、空白の有意なコンテンツ (を持つコレクションによって保持されるコンテンツ) 内で子要素として表示される可能性のある特定の型に適用され <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is applied to specific types that might appear as child elements within white-space significant content (content held by a collection that has <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>).</span></span> <span data-ttu-id="dd793-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> は、主に保存パスに関連しますが、を調べることによって、読み込みパスの XAML 型システムで使用でき <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is mainly relevant to the save path, but is available in the XAML type system in the load path by examining <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dd793-188">詳細については、「 [XAML での空白の処理](white-space-processing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd793-188">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="typeconverterattribute"></a><span data-ttu-id="dd793-189">TypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-189">TypeConverterAttribute</span></span>

<span data-ttu-id="dd793-190">**リファレンスドキュメント:**  <xref:System.ComponentModel.TypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-190">**Reference Documentation:**  <xref:System.ComponentModel.TypeConverterAttribute></span></span>

<span data-ttu-id="dd793-191">**適用対象:** クラス、プロパティ、メソッド (唯一の XAML 有効なメソッドケースは、 `get` アタッチ可能なメンバーをサポートするアクセサーです)。</span><span class="sxs-lookup"><span data-stu-id="dd793-191">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="dd793-192">**引数:**<xref:System.Type>の <xref:System.ComponentModel.TypeConverter> 。</span><span class="sxs-lookup"><span data-stu-id="dd793-192">**Arguments:** The <xref:System.Type> of the <xref:System.ComponentModel.TypeConverter>.</span></span>

<span data-ttu-id="dd793-193"><xref:System.ComponentModel.TypeConverterAttribute> XAML コンテキストでは、カスタムを参照し <xref:System.ComponentModel.TypeConverter> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-193"><xref:System.ComponentModel.TypeConverterAttribute> in a XAML context references a custom <xref:System.ComponentModel.TypeConverter>.</span></span> <span data-ttu-id="dd793-194">これ <xref:System.ComponentModel.TypeConverter> により、カスタム型の型変換動作、またはその型のメンバーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-194">This <xref:System.ComponentModel.TypeConverter> provides type conversion behavior for custom types, or members of that type.</span></span>

<span data-ttu-id="dd793-195"><xref:System.ComponentModel.TypeConverterAttribute>型コンバーターの実装を参照して、属性を型に適用します。</span><span class="sxs-lookup"><span data-stu-id="dd793-195">Apply the <xref:System.ComponentModel.TypeConverterAttribute> attribute to your type, referencing your type converter implementation.</span></span> <span data-ttu-id="dd793-196">XAML の型コンバーターは、クラス、構造体、またはインターフェイスで定義できます。</span><span class="sxs-lookup"><span data-stu-id="dd793-196">You can define type converters for XAML on classes, structures, or interfaces.</span></span> <span data-ttu-id="dd793-197">列挙型の型変換を指定する必要はありません。変換はネイティブで有効になります。</span><span class="sxs-lookup"><span data-stu-id="dd793-197">You do not need to provide type conversion for enumerations, that conversion is enabled natively.</span></span>

<span data-ttu-id="dd793-198">型コンバーターは、マークアップ内の属性または初期化テキストに使用される文字列から目的の型に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-198">Your type converter should be able to convert from a string that is used for attributes or initialization text in markup, into your intended destination type.</span></span> <span data-ttu-id="dd793-199">詳細については、「 [TypeConverters AND XAML](../framework/wpf/advanced/typeconverters-and-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd793-199">For more information, see [TypeConverters and XAML](../framework/wpf/advanced/typeconverters-and-xaml.md).</span></span>

<span data-ttu-id="dd793-200">型のすべての値にを適用するのではなく、XAML の型コンバーターの動作を特定のプロパティに対して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd793-200">Rather than applying to all values of a type, a type converter behavior for XAML can also be established on a specific property.</span></span> <span data-ttu-id="dd793-201">この場合は、 <xref:System.ComponentModel.TypeConverterAttribute> プロパティ定義 (特定のおよび定義ではなく、外側の定義) にを適用し `get` `set` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-201">In this case, you apply <xref:System.ComponentModel.TypeConverterAttribute> to the property definition (the outer definition, not the specific `get` and `set` definitions).</span></span>

<span data-ttu-id="dd793-202">カスタムアタッチ可能なメンバーの XAML 使用に対する型コンバーターの動作は、 <xref:System.ComponentModel.TypeConverterAttribute> `get` xaml の使用をサポートするメソッドアクセサーにを適用することによって割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dd793-202">A type converter behavior for XAML usage of a custom attachable member can be assigned by applying <xref:System.ComponentModel.TypeConverterAttribute> to the `get` method accessor that supports the XAML usage.</span></span>

<span data-ttu-id="dd793-203">と同様に <xref:System.ComponentModel.TypeConverter> 、 <xref:System.ComponentModel.TypeConverterAttribute> XAML が存在する前に .net に存在し、型コンバーターモデルによって他の目的が提供されました。</span><span class="sxs-lookup"><span data-stu-id="dd793-203">Similar to <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existed in .NET prior to the existence of XAML, and the type converter model served other purposes.</span></span> <span data-ttu-id="dd793-204">を参照して使用するに <xref:System.ComponentModel.TypeConverterAttribute> は、を完全修飾するか、またはのステートメントを指定する必要があり `using` <xref:System.ComponentModel> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-204">In order to reference and use <xref:System.ComponentModel.TypeConverterAttribute>, you must fully qualify it or provide a `using` statement for <xref:System.ComponentModel>.</span></span> <span data-ttu-id="dd793-205">また、プロジェクトにシステムアセンブリを含めます。</span><span class="sxs-lookup"><span data-stu-id="dd793-205">Also include the System assembly in your project.</span></span>

### <a name="uidpropertyattribute"></a><span data-ttu-id="dd793-206">UidPropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-206">UidPropertyAttribute</span></span>

<span data-ttu-id="dd793-207">**リファレンスドキュメント:**  <xref:System.Windows.Markup.UidPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-207">**Reference Documentation:**  <xref:System.Windows.Markup.UidPropertyAttribute></span></span>

<span data-ttu-id="dd793-208">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-208">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-209">**引数:** 関連するプロパティを名前で参照する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-209">**Arguments:** A string that references the relevant property by name.</span></span>

<span data-ttu-id="dd793-210">[X:Uid ディレクティブ](xuid-directive.md)にエイリアスを指定するクラスの CLR プロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="dd793-210">Indicates the CLR property of a class that aliases the [x:Uid Directive](xuid-directive.md).</span></span>

### <a name="usableduringinitializationattribute"></a><span data-ttu-id="dd793-211">UsableDuringInitializationAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-211">UsableDuringInitializationAttribute</span></span>

<span data-ttu-id="dd793-212">**リファレンスドキュメント:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-212">**Reference Documentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span></span>

<span data-ttu-id="dd793-213">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-213">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-214">**引数:** ブール値。</span><span class="sxs-lookup"><span data-stu-id="dd793-214">**Arguments:** A Boolean.</span></span> <span data-ttu-id="dd793-215">属性の目的で使用する場合は、値をに設定する必要があり `true` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-215">If used for the attribute's intended purpose, the value should be set to `true`.</span></span>

<span data-ttu-id="dd793-216">XAML オブジェクトグラフの作成中に、型が上から下に構築されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dd793-216">Indicates whether the type is built top-down during XAML object graph creation.</span></span> <span data-ttu-id="dd793-217">これは高度な概念であり、プログラミングモデルの定義と密接に関連していると考えられます。</span><span class="sxs-lookup"><span data-stu-id="dd793-217">This is an advanced concept, which is probably closely related to the definition of your programming model.</span></span> <span data-ttu-id="dd793-218">詳細については、「<xref:System.Windows.Markup.UsableDuringInitializationAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd793-218">For more information, see <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.</span></span>

### <a name="valueserializerattribute"></a><span data-ttu-id="dd793-219">の属性</span><span class="sxs-lookup"><span data-stu-id="dd793-219">ValueSerializerAttribute</span></span>

<span data-ttu-id="dd793-220">**リファレンスドキュメント:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-220">**Reference Documentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span></span>

<span data-ttu-id="dd793-221">**適用対象:** クラス、プロパティ、メソッド (唯一の XAML 有効なメソッドケースは、 `get` アタッチ可能なメンバーをサポートするアクセサーです)。</span><span class="sxs-lookup"><span data-stu-id="dd793-221">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="dd793-222">**引数:**<xref:System.Type>属性付きの型のすべてのプロパティ、または特定の属性付きプロパティをシリアル化するときに使用する値シリアライザーサポートクラスを指定する。</span><span class="sxs-lookup"><span data-stu-id="dd793-222">**Arguments:** A <xref:System.Type> that specifies the value serializer support class to use when serializing all properties of the attributed type, or the specific attributed property.</span></span>

<span data-ttu-id="dd793-223"><xref:System.Windows.Markup.ValueSerializer> よりも多くの状態とコンテキストを必要とする値シリアル化クラスを指定し <xref:System.ComponentModel.TypeConverter> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-223"><xref:System.Windows.Markup.ValueSerializer> specifies a value serialization class that requires more state and context than a <xref:System.ComponentModel.TypeConverter> does.</span></span> <span data-ttu-id="dd793-224"><xref:System.Windows.Markup.ValueSerializer> アタッチ可能なメンバー <xref:System.Windows.Markup.ValueSerializerAttribute> の静的アクセサーメソッドに属性を適用することによって、アタッチできるメンバーに関連付けることができ `get` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-224"><xref:System.Windows.Markup.ValueSerializer> can be associated with an attachable member by applying the <xref:System.Windows.Markup.ValueSerializerAttribute> attribute on the static `get` accessor method for the attachable member.</span></span> <span data-ttu-id="dd793-225">値のシリアル化は、列挙型、インターフェイス、および構造体にも適用できますが、デリゲートには適用できません。</span><span class="sxs-lookup"><span data-stu-id="dd793-225">Value serialization is also applicable for enumerations, interfaces, and structures, but not for delegates.</span></span>

### <a name="whitespacesignificantcollectionattribute"></a><span data-ttu-id="dd793-226">WhitespaceSignificantCollectionAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-226">WhitespaceSignificantCollectionAttribute</span></span>

<span data-ttu-id="dd793-227">**リファレンスドキュメント:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-227">**Reference Documentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span></span>

<span data-ttu-id="dd793-228">**適用対象:** クラス。特に、混合コンテンツをホストすることが想定されているコレクション型。 UI 表現では、オブジェクト要素を囲む空白文字が重要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="dd793-228">**Applies to:** Class, specifically collection types that are expected to host mixed content, where white space around object elements might be significant for UI representation.</span></span>

<span data-ttu-id="dd793-229">**引数:** 存在.</span><span class="sxs-lookup"><span data-stu-id="dd793-229">**Arguments:** None.</span></span>

<span data-ttu-id="dd793-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> コレクション型を XAML プロセッサによって有意な空白として処理する必要があることを示します。これは、コレクション内の XAML ノードストリームの値ノードの構築に影響します。</span><span class="sxs-lookup"><span data-stu-id="dd793-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indicates that a collection type should be processed as white-space significant by a XAML processor, which influences the construction of the XAML node stream's value nodes within the collection.</span></span> <span data-ttu-id="dd793-231">詳細については、「 [XAML での空白の処理](white-space-processing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd793-231">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="xamldeferloadattribute"></a><span data-ttu-id="dd793-232">XamlDeferLoadAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-232">XamlDeferLoadAttribute</span></span>

<span data-ttu-id="dd793-233">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-233">**Reference Documentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span></span>

<span data-ttu-id="dd793-234">**適用対象:** クラス、プロパティ。</span><span class="sxs-lookup"><span data-stu-id="dd793-234">**Applies to:** Class, property.</span></span>

<span data-ttu-id="dd793-235">**引数:** は、文字列として、またはとして型として、2つの属性フォーム型をサポートし <xref:System.Type> ます</span><span class="sxs-lookup"><span data-stu-id="dd793-235">**Arguments:** Supports two attribution forms types as strings, or types as <xref:System.Type>.</span></span> <span data-ttu-id="dd793-236">以下を参照してください。<xref:System.Windows.Markup.XamlDeferLoadAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-236">See <xref:System.Windows.Markup.XamlDeferLoadAttribute>.</span></span>

<span data-ttu-id="dd793-237">クラスまたはプロパティに XAML の遅延読み込みの使用 (テンプレート動作など) が含まれていることを示し、遅延動作を有効にするクラスと、その宛先/コンテンツ タイプを報告します。</span><span class="sxs-lookup"><span data-stu-id="dd793-237">Indicates that a class or property has a deferred load usage for XAML (such as a template behavior), and reports the class that enables the deferring behavior and its destination/content type.</span></span>

### <a name="xamlsetmarkupextensionattribute"></a><span data-ttu-id="dd793-238">System.windows.markup.xamlsetmarkupextensionattribute</span><span class="sxs-lookup"><span data-stu-id="dd793-238">XamlSetMarkupExtensionAttribute</span></span>

<span data-ttu-id="dd793-239">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-239">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span></span>

<span data-ttu-id="dd793-240">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-240">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-241">**引数:** コールバックに名前を付いています。</span><span class="sxs-lookup"><span data-stu-id="dd793-241">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="dd793-242">クラスがマークアップ拡張機能を使用して1つ以上のプロパティに値を提供できること、およびクラスの任意のプロパティに対してマークアップ拡張機能のセット操作を実行する前に XAML ライターが呼び出す必要があるハンドラーを参照することを示します。</span><span class="sxs-lookup"><span data-stu-id="dd793-242">Indicates that a class can use a markup extension to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a markup extension set operation on any property of the class.</span></span>

### <a name="xamlsettypeconverterattribute"></a><span data-ttu-id="dd793-243">XamlSetTypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-243">XamlSetTypeConverterAttribute</span></span>

<span data-ttu-id="dd793-244">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-244">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span></span>

<span data-ttu-id="dd793-245">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-245">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-246">**引数:** コールバックに名前を付いています。</span><span class="sxs-lookup"><span data-stu-id="dd793-246">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="dd793-247">クラスが型コンバーターを使用して1つ以上のプロパティに値を提供できることを示します。また、クラスの任意のプロパティに対して型コンバーターの設定操作を実行する前に、XAML ライターが呼び出すハンドラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="dd793-247">Indicates that a class can use a type converter to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a type converter set operation on any property of the class.</span></span>

### <a name="xmllangpropertyattribute"></a><span data-ttu-id="dd793-248">XmlLangPropertyAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-248">XmlLangPropertyAttribute</span></span>

<span data-ttu-id="dd793-249">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-249">**Reference Documentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span></span>

<span data-ttu-id="dd793-250">**適用対象:** 講義</span><span class="sxs-lookup"><span data-stu-id="dd793-250">**Applies to:** Class</span></span>

<span data-ttu-id="dd793-251">**引数:** 属性付きの型に対してエイリアスを付けるプロパティの名前を指定する文字列 `xml:lang` 。</span><span class="sxs-lookup"><span data-stu-id="dd793-251">**Arguments:** A string that specifies the name of the property to alias to `xml:lang` on the attributed type.</span></span>

<span data-ttu-id="dd793-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> XML ディレクティブにマップされる属性付きの型のプロパティを報告し `lang` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> reports a property of the attributed type that maps to the XML `lang` directive.</span></span> <span data-ttu-id="dd793-253">プロパティは必ずしも型であるとは限りません <xref:System.String> が、文字列から割り当て可能にする必要があります (代入は、型コンバーターをプロパティの型または特定のプロパティに関連付けることによって実現できます)。</span><span class="sxs-lookup"><span data-stu-id="dd793-253">The property is not necessarily of type <xref:System.String> but must be assignable from a string (assignment could be accomplished by associating a type converter with the property's type or with the specific property).</span></span> <span data-ttu-id="dd793-254">プロパティは、読み取り/書き込み可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-254">The property must be read/write.</span></span>

<span data-ttu-id="dd793-255">マッピングのシナリオ `xml:lang` は、ランタイムオブジェクトモデルが、具体的には XMLDOM で処理することなく、XML で指定された言語情報にアクセスできるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="dd793-255">The scenario for mapping `xml:lang` is so that a runtime object model has access to XML-specified language information without specifically processing with an XMLDOM.</span></span>

<span data-ttu-id="dd793-256">定義は、定義する型に割り当て可能なすべての派生型に継承されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-256">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="dd793-257">特定の派生型にを適用することで、特定の派生型の定義をオーバーライドできますが、これ <xref:System.Windows.Markup.XmlLangPropertyAttribute> は一般的なシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="dd793-257">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> on the specific derived type, although that is an uncommon scenario.</span></span>

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a><span data-ttu-id="dd793-258">アセンブリレベルでの CLR 属性の XAML-Related</span><span class="sxs-lookup"><span data-stu-id="dd793-258">XAML-Related CLR Attributes at the Assembly Level</span></span>

<span data-ttu-id="dd793-259">以下のセクションでは、型またはメンバーの定義には適用されず、代わりにアセンブリに適用される XAML 関連の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd793-259">The following sections describe the XAML-related attributes that are not applied to types or member definitions, but are instead applied to assemblies.</span></span> <span data-ttu-id="dd793-260">これらの属性は、XAML で使用するカスタム型を含むライブラリを定義する全体的な目標に関連します。</span><span class="sxs-lookup"><span data-stu-id="dd793-260">These attributes are pertinent to the overall goal of defining a library that contains custom types to use in XAML.</span></span> <span data-ttu-id="dd793-261">属性の一部は、必ずしも XAML ノードストリームに直接影響するわけではありませんが、他のコンシューマーが使用できるようにノードストリームで渡されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-261">Some of the attributes do not necessarily influence the XAML node stream directly, but are passed on in the node stream for other consumers to use.</span></span> <span data-ttu-id="dd793-262">この情報のコンシューマーには、XAML 名前空間情報と関連するプレフィックス情報を必要とするデザイン環境またはシリアル化プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd793-262">Consumers for the information include design environments or serialization processes that need XAML namespace information and associated prefix information.</span></span> <span data-ttu-id="dd793-263">XAML スキーマコンテキスト (.NET XAML サービスの既定値を含む) も、この情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd793-263">A XAML schema context (including the .NET XAML Services default) also uses this information.</span></span>

### <a name="xmlnscompatiblewithattribute"></a><span data-ttu-id="dd793-264">Xmlns/Withattribute</span><span class="sxs-lookup"><span data-stu-id="dd793-264">XmlnsCompatibleWithAttribute</span></span>

<span data-ttu-id="dd793-265">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-265">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span></span>

<span data-ttu-id="dd793-266">**引数:**</span><span class="sxs-lookup"><span data-stu-id="dd793-266">**Arguments:**</span></span>

- <span data-ttu-id="dd793-267">適用する XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-267">A string that specifies the identifier of the XAML namespace to subsume.</span></span>

- <span data-ttu-id="dd793-268">前の引数から XAML 名前空間を適用できる XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-268">A string that specifies the identifier of the XAML namespace that can subsume the XAML namespace from the previous argument.</span></span>

  <span data-ttu-id="dd793-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> XAML 名前空間を別の XAML 名前空間で包括ことができることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> specifies that a XAML namespace can be subsumed by another XAML namespace.</span></span> <span data-ttu-id="dd793-270">通常、包含する側の XAML 名前空間は、あらかじめ定義した <xref:System.Windows.Markup.XmlnsDefinitionAttribute> で示されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-270">Typically, the subsuming XAML namespace is indicated in a previously defined <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span> <span data-ttu-id="dd793-271">この手法を使用すると、ライブラリ内の XAML ボキャブラリのバージョンを管理し、以前にバージョン管理されたボキャブラリに対して以前に定義したマークアップと互換性を持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="dd793-271">This technique can be used for versioning a XAML vocabulary in a library and to make it compatible with previously defined markup against the earlier versioned vocabulary.</span></span>

### <a name="xmlnsdefinitionattribute"></a><span data-ttu-id="dd793-272">XmlnsDefinitionAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-272">XmlnsDefinitionAttribute</span></span>

<span data-ttu-id="dd793-273">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-273">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span></span>

<span data-ttu-id="dd793-274">**引数:**</span><span class="sxs-lookup"><span data-stu-id="dd793-274">**Arguments:**</span></span>

- <span data-ttu-id="dd793-275">定義する XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-275">A string that specifies the identifier of the XAML namespace to define.</span></span>

- <span data-ttu-id="dd793-276">CLR 名前空間に名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-276">A string that names a CLR namespace.</span></span> <span data-ttu-id="dd793-277">CLR 名前空間はアセンブリでパブリック型を定義する必要があります。また、CLR 名前空間の型のうち少なくとも1つが XAML の使用を想定している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-277">The CLR namespace should define public types in your assembly, and at least one of the CLR namespace types should be intended for XAML usage.</span></span>

  <span data-ttu-id="dd793-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 名前空間と CLR 名前空間の間のアセンブリごとのマッピングを指定します。これは xaml オブジェクトライターまたは XAML スキーマコンテキストによる型の解決に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd793-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a mapping on a per-assembly basis between a XAML namespace and a CLR namespace, which is then used for type resolution by a XAML object writer or XAML schema context.</span></span>

  <span data-ttu-id="dd793-279">1つの <xref:System.Windows.Markup.XmlnsDefinitionAttribute> アセンブリに複数のを適用できます。</span><span class="sxs-lookup"><span data-stu-id="dd793-279">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="dd793-280">これは、次のいずれかの理由で実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-280">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="dd793-281">ライブラリの設計には、実行時 API アクセスの論理組織用に複数の CLR 名前空間が含まれています。ただし、同じ XAML 名前空間を参照することによって、これらの名前空間のすべての型を XAML で使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-281">The library design contains multiple CLR namespaces for logical organization of run-time API access; however, you want all types in those namespaces to be XAML-usable by referencing the same XAML namespace.</span></span> <span data-ttu-id="dd793-282">この場合、 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 同じ値を使用して複数の属性を適用し <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> ますが、値は異なり <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-282">In this case, you apply several <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributes using the same <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value but different <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> values.</span></span> <span data-ttu-id="dd793-283">これは、フレームワークまたはアプリケーションが一般的な使用法で既定の XAML 名前空間として意図している XAML 名前空間のマッピングを定義する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="dd793-283">This is especially useful if you are defining mappings for the XAML namespace that your framework or application intends to be the default XAML namespace in common usage.</span></span>

- <span data-ttu-id="dd793-284">ライブラリの設計には複数の CLR 名前空間が含まれており、これらの CLR 名前空間の型の使用について、意図的に XAML 名前空間を分離する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-284">The library design contains multiple CLR namespaces, and you want a deliberate XAML namespace separation between the usages of types in those CLR namespaces.</span></span>

- <span data-ttu-id="dd793-285">アセンブリに CLR 名前空間を定義し、複数の XAML 名前空間からアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="dd793-285">You define a CLR namespace in the assembly, and you want it to be accessible through more than one XAML namespace.</span></span> <span data-ttu-id="dd793-286">このシナリオは、同じコードベースを持つ複数のボキャブラリをサポートする場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="dd793-286">This scenario occurs when you are supporting multiple vocabularies with the same codebase.</span></span>

- <span data-ttu-id="dd793-287">XAML 言語サポートは、1つまたは複数の CLR 名前空間で定義します。</span><span class="sxs-lookup"><span data-stu-id="dd793-287">You define XAML language support in one or more CLR namespaces.</span></span> <span data-ttu-id="dd793-288">この場合、値はになり <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> `http://schemas.microsoft.com/winfx/2006/xaml` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-288">In this case, the <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value should be `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span>

### <a name="xmlnsprefixattribute"></a><span data-ttu-id="dd793-289">XmlnsPrefixAttribute</span><span class="sxs-lookup"><span data-stu-id="dd793-289">XmlnsPrefixAttribute</span></span>

<span data-ttu-id="dd793-290">**リファレンスドキュメント:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span><span class="sxs-lookup"><span data-stu-id="dd793-290">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span></span>

<span data-ttu-id="dd793-291">**引数:**</span><span class="sxs-lookup"><span data-stu-id="dd793-291">**Arguments:**</span></span>

- <span data-ttu-id="dd793-292">XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-292">A string that specifies the identifier of a XAML namespace.</span></span>

- <span data-ttu-id="dd793-293">推奨されるプレフィックスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dd793-293">A string that specifies a recommended prefix.</span></span>

  <span data-ttu-id="dd793-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 名前空間に使用する推奨プレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd793-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a recommended prefix to use for a XAML namespace.</span></span> <span data-ttu-id="dd793-295">プレフィックスは、.NET XAML サービスによってシリアル化される XAML ファイルに要素や属性を書き込む場合や、xaml を <xref:System.Xaml.XamlXmlWriter> 実装するライブラリが xaml 編集機能を持つデザイン環境と対話する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dd793-295">The prefix is useful when writing elements and attributes in a XAML file that is serialized by .NET XAML Services <xref:System.Xaml.XamlXmlWriter>, or when a XAML-implementing library interacts with a design environment that has XAML editing features.</span></span>

  <span data-ttu-id="dd793-296">1つの <xref:System.Windows.Markup.XmlnsPrefixAttribute> アセンブリに複数のを適用できます。</span><span class="sxs-lookup"><span data-stu-id="dd793-296">More than one <xref:System.Windows.Markup.XmlnsPrefixAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="dd793-297">これは、次のいずれかの理由で実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd793-297">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="dd793-298">アセンブリでは、複数の XAML 名前空間の型が定義されています。</span><span class="sxs-lookup"><span data-stu-id="dd793-298">Your assembly defines types for more than one XAML namespace.</span></span> <span data-ttu-id="dd793-299">この場合は、XAML 名前空間ごとに異なるプレフィックス値を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd793-299">In this case, define different prefix values for each XAML namespace.</span></span>

- <span data-ttu-id="dd793-300">複数のボキャブラリをサポートし、各ボキャブラリと XAML 名前空間に異なるプレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd793-300">You are supporting multiple vocabularies, and you use different prefixes for each vocabulary and XAML namespace.</span></span>

- <span data-ttu-id="dd793-301">アセンブリに XAML 言語サポートを定義し、にを設定し <xref:System.Windows.Markup.XmlnsDefinitionAttribute> `http://schemas.microsoft.com/winfx/2006/xaml` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-301">You define XAML language support in the assembly and have a <xref:System.Windows.Markup.XmlnsDefinitionAttribute> for `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span> <span data-ttu-id="dd793-302">この場合は、通常、プレフィックスを昇格させる必要があり `x` ます。</span><span class="sxs-lookup"><span data-stu-id="dd793-302">In this case, you typically should promote the prefix `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="dd793-303">.NET XAML サービスでは、XAML 関連の属性も定義 <xref:System.Windows.Markup.RootNamespaceAttribute> します。</span><span class="sxs-lookup"><span data-stu-id="dd793-303">.NET XAML Services also defines the XAML-related attribute <xref:System.Windows.Markup.RootNamespaceAttribute>.</span></span> <span data-ttu-id="dd793-304">この属性は、プロジェクトシステムサポートのアセンブリレベルの属性であり、XAML カスタム型には関連しません。</span><span class="sxs-lookup"><span data-stu-id="dd793-304">This attribute is an assembly-level attribute for project system support, and it is not relevant for XAML custom types.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd793-305">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd793-305">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="dd793-306">.NET XAML サービスで使用するカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="dd793-306">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
