---
title: Windows Presentation Foundation の概要
description: この記事では、.NET に関連した Windows Presentation Foundation (WPF) の概要と、提供される機能について説明します。
ms.date: 07/18/2019
ms.topic: overview
ms.openlocfilehash: f548299dd259ab5f52962660cc7e342396e20213
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992873"
---
# <a name="what-is-windows-presentation-foundation-wpf-net"></a><span data-ttu-id="7f539-103">Windows Presentation Foundation (WPF .NET) とは</span><span class="sxs-lookup"><span data-stu-id="7f539-103">What is Windows Presentation Foundation (WPF .NET)</span></span>

<span data-ttu-id="7f539-104">Windows 用のデスクトップ クライアント アプリケーションを作成する UI フレームワークである、Windows Presentation Foundation (WPF) のデスクトップ ガイドです。</span><span class="sxs-lookup"><span data-stu-id="7f539-104">Welcome to the Desktop Guide for Windows Presentation Foundation (WPF), a UI framework that creates desktop client applications for Windows.</span></span> <span data-ttu-id="7f539-105">WPF の開発プラットフォームでは、アプリケーション モデル、コントロール、グラフィックス、データ バインディングなどのさまざまなアプリケーション開発機能の一式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7f539-105">The WPF development platform supports a broad set of application development features, including an application model, controls, graphics, and data binding.</span></span> <span data-ttu-id="7f539-106">WPF では、Extensible Application Markup Language (XAML) の使用により、アプリケーションのプログラミング用の宣言型モデルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-106">WPF uses Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="7f539-107">WPF には、2 つの実装があります。</span><span class="sxs-lookup"><span data-stu-id="7f539-107">There are two implementations of WPF:</span></span>

01. <span data-ttu-id="7f539-108">[GitHub](https://github.com/dotnet/wpf) 上でホストされる、オープンソース実装。</span><span class="sxs-lookup"><span data-stu-id="7f539-108">The open-source implementation hosted on [GitHub](https://github.com/dotnet/wpf).</span></span> <span data-ttu-id="7f539-109">このバージョンは .NET Core 3.0 で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-109">This version runs on .NET Core 3.0.</span></span> <span data-ttu-id="7f539-110">XAML 用の WPF ビジュアル デザイナーでは、少なくとも [Visual Studio 2019 バージョン 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide) が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f539-110">The WPF Visual Designer for XAML requires, at a minimum, [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide).</span></span>

01. <span data-ttu-id="7f539-111">Visual Studio 2019 および Visual Studio 2017 でサポートされている、.NET Framework 実装。</span><span class="sxs-lookup"><span data-stu-id="7f539-111">The .NET Framework implementation that's supported by Visual Studio 2019 and Visual Studio 2017.</span></span>

<span data-ttu-id="7f539-112">このデスクトップ ガイドは、.NET Core 3.0 と WPF 向けに書かれています。</span><span class="sxs-lookup"><span data-stu-id="7f539-112">This Desktop Guide is written for .NET Core 3.0 and WPF.</span></span> <span data-ttu-id="7f539-113">.NET Framework を使用した WPF に関する既存のドキュメントの詳細については、「[Framework Windows Presentation Foundation](../../../framework/wpf/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f539-113">For more information about the existing documentation for WPF with the .NET Framework, see [Framework Windows Presentation Foundation](../../../framework/wpf/index.md).</span></span>

## <a name="xaml"></a><span data-ttu-id="7f539-114">XAML</span><span class="sxs-lookup"><span data-stu-id="7f539-114">XAML</span></span>

<span data-ttu-id="7f539-115">XAML は、WPF でリソースや UI 要素の定義などを行うために使用される、宣言型の XML ベースの言語です。</span><span class="sxs-lookup"><span data-stu-id="7f539-115">XAML is a declarative XML-based language that WPF uses for things such as defining resources or UI elements.</span></span> <span data-ttu-id="7f539-116">XAML で定義された要素は、アセンブリからのオブジェクトのインスタンス化を表します。</span><span class="sxs-lookup"><span data-stu-id="7f539-116">Elements defined in XAML represent the instantiation of objects from an assembly.</span></span> <span data-ttu-id="7f539-117">XAML は、バッキング型システムへの直接の結びつきのない、実行時に解釈される他のほとんどのマークアップ言語とは異なります。</span><span class="sxs-lookup"><span data-stu-id="7f539-117">XAML is unlike most other markup languages, which are interpreted at runtime without a direct tie to a backing type system.</span></span>

<span data-ttu-id="7f539-118">次の例は、UI の一部としてボタンを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f539-118">The following example shows how you would create a button as part of a UI.</span></span> <span data-ttu-id="7f539-119">この例は、XAML でオブジェクトを表す方法を示すことを目的としています。`Button` は型、`Content` はプロパティです。</span><span class="sxs-lookup"><span data-stu-id="7f539-119">This example is intended to give you an idea of how XAML represents an object, where `Button` is the type and `Content` is a property.</span></span>

```xaml
<StackPanel>
    <Button Content="Click Me!" />
</StackPanel>
```

<!--For more information, see [XAML overview (WPF)](../../../framework/wpf/advanced/xaml-overview-wpf.md).-->

### <a name="xaml-extensions"></a><span data-ttu-id="7f539-120">XAML 拡張機能</span><span class="sxs-lookup"><span data-stu-id="7f539-120">XAML extensions</span></span>

<span data-ttu-id="7f539-121">XAML には、マークアップ拡張の構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f539-121">XAML provides syntax for markup extensions.</span></span> <span data-ttu-id="7f539-122">マークアップ拡張を使用すると、属性形式またはプロパティ要素形式、あるいはその両方で、プロパティの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-122">Markup extensions can be used to provide values for properties in attribute form, property-element form, or both.</span></span>

<span data-ttu-id="7f539-123">たとえば、前の XAML コードでは、表示されるコンテンツがリテラル文字列 `"Click Me!"` に設定されたボタンを定義しましたが、代わりにコンテンツをサポートされているマークアップ拡張によって設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f539-123">For example, the previous XAML code defined a button with the visible content set to the literal string `"Click Me!"`, but the content can be instead set by a supported markup extension.</span></span> <span data-ttu-id="7f539-124">マークアップ拡張は、左中かっこと右中かっこ `{ }` を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-124">A markup extension is defined with opening and closing curly braces `{ }`.</span></span> <span data-ttu-id="7f539-125">その後、マークアップ拡張の種類は、左中かっこの直後の文字列トークンによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-125">The type of markup extension is then identified by the string token immediately following the opening curly brace.</span></span>

```xaml
<StackPanel>
    <Button Content="{MarkupType}" />
</StackPanel>
```

<span data-ttu-id="7f539-126">WPF には、データ バインディング用の `{Binding}` など、さまざまな XAML 用マークアップ拡張が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f539-126">WPF provides different markup extensions for XAML such as `{Binding}` for data binding.</span></span>

<span data-ttu-id="7f539-127">詳細については、「[マークアップ拡張機能と WPF XAML](../../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f539-127">For more information, see [Markup Extensions and WPF XAML](../../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="property-system"></a><span data-ttu-id="7f539-128">プロパティ システム</span><span class="sxs-lookup"><span data-stu-id="7f539-128">Property system</span></span>

<span data-ttu-id="7f539-129">WPF には、型の[プロパティ](/dotnet/standard/base-types/common-type-system#properties)の機能を拡張するために使用できる一連のサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f539-129">WPF provides a set of services that can be used to extend the functionality of a type's [property](/dotnet/standard/base-types/common-type-system#properties).</span></span> <span data-ttu-id="7f539-130">これらのサービスはまとめて *WPF プロパティ システム* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7f539-130">Collectively, these services are referred to as the *WPF property system*.</span></span> <span data-ttu-id="7f539-131">WPF プロパティ システムによって使用されるプロパティは、依存関係プロパティと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="7f539-131">A property that is backed by the WPF property system is known as a dependency property.</span></span>

<span data-ttu-id="7f539-132">依存関係プロパティでは、プロパティをバッキングする <xref:System.Windows.DependencyProperty> 型の提供によって、プロパティ機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-132">Dependency properties extend property functionality by providing the <xref:System.Windows.DependencyProperty> type that backs a property.</span></span> <span data-ttu-id="7f539-133">依存関係プロパティの型は、プライベート フィールドでプロパティをバッキングする標準パターンの代替実装です。</span><span class="sxs-lookup"><span data-stu-id="7f539-133">The dependency property type is an alternative implementation of the standard pattern of backing the property with a private field.</span></span>

### <a name="dependency-property"></a><span data-ttu-id="7f539-134">依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="7f539-134">Dependency property</span></span>

<span data-ttu-id="7f539-135">WPF では通常、依存関係プロパティは標準の .NET [プロパティ](/dotnet/standard/base-types/common-type-system#properties)として公開されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-135">In WPF, dependency properties are typically exposed as standard .NET [properties](/dotnet/standard/base-types/common-type-system#properties).</span></span> <span data-ttu-id="7f539-136">基本的なレベルでは、これらのプロパティを直接操作することができます。これらが依存関係プロパティとして実装されることは意識しません。</span><span class="sxs-lookup"><span data-stu-id="7f539-136">At a basic level, you could interact with these properties directly and never know that they're implemented as a dependency property.</span></span>

<span data-ttu-id="7f539-137">依存関係プロパティの目的は、他の入力の値に基づいてプロパティの値を計算する方法を提供することです。</span><span class="sxs-lookup"><span data-stu-id="7f539-137">The purpose of dependency properties is to provide a way to compute the value of a property based on the value of other inputs.</span></span> <span data-ttu-id="7f539-138">これらの他の入力には、テーマやユーザー設定などのシステム プロパティや、データ バインディングやアニメーションからの Just-In-Time プロパティなどがあります。</span><span class="sxs-lookup"><span data-stu-id="7f539-138">These other inputs might include system properties such as themes and user preferences, or just-in-time property from data binding and animations.</span></span>

<span data-ttu-id="7f539-139">依存関係プロパティを実装して、検証、既定値、他のプロパティに対する変更を監視するコールバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-139">A dependency property can be implemented to provide validation, default values, and callbacks that monitor changes to other properties.</span></span> <span data-ttu-id="7f539-140">新しいプロパティを作成したり既存のプロパティをオーバーライドしたりするのではなく、依存関係プロパティ メタデータをオーバーライドすることによって、派生クラスで既存のプロパティの特定の特性を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f539-140">Derived classes can also change some specific characteristics of an existing property by overriding dependency property metadata, rather than creating a new property or overriding an existing property.</span></span>

### <a name="dependency-object"></a><span data-ttu-id="7f539-141">依存関係オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7f539-141">Dependency object</span></span>

<span data-ttu-id="7f539-142">WPF プロパティ システムにとって重要なもう 1 つの型は、<xref:System.Windows.DependencyObject> です。</span><span class="sxs-lookup"><span data-stu-id="7f539-142">Another type that is key to the WPF property system is the <xref:System.Windows.DependencyObject>.</span></span> <span data-ttu-id="7f539-143">この型では、依存関係プロパティを登録および所有できる基本クラスが定義されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-143">This type defines the base class that can register and own a dependency property.</span></span> <span data-ttu-id="7f539-144"><xref:System.Windows.DependencyObject.GetValue%2A> と <xref:System.Windows.DependencyObject.SetValue%2A> メソッドにより、依存関係オブジェクト インスタンスの依存関係プロパティのバッキング実装が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-144">The <xref:System.Windows.DependencyObject.GetValue%2A> and <xref:System.Windows.DependencyObject.SetValue%2A> methods provide the backing implementation of the dependency property for the dependency object instance.</span></span>

<span data-ttu-id="7f539-145">次の例は、`ValueProperty` という名前の単一の依存関係プロパティ識別子を定義する依存関係オブジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="7f539-145">The following example shows a dependency object that defines a single dependency property identifier named `ValueProperty`.</span></span> <span data-ttu-id="7f539-146">依存関係プロパティは、`Value` .NET プロパティを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-146">The dependency property is created with the `Value` .NET property.</span></span>

```csharp
public class TextField: DependencyObject
{
    public static readonly DependencyProperty ValueProperty =
        DependencyProperty.Register("Value", typeof(string), typeof(TextField), new PropertyMetadata(""));

    public string Value
    {
        get { return (string)GetValue(ValueProperty); }
        set { SetValue(ValueProperty, value); }
    }
}
```

<span data-ttu-id="7f539-147">依存関係プロパティは、上の例の `TextField` のように、依存関係オブジェクト型の静的メンバーとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-147">The dependency property is defined as a static member of a dependency object type, such as `TextField` in example above.</span></span> <span data-ttu-id="7f539-148">依存関係プロパティは、依存関係オブジェクトを使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f539-148">The dependency property must be registered with the dependency object.</span></span>

<span data-ttu-id="7f539-149">上の例の `Value` プロパティにより依存関係プロパティがラップされるため、使い慣れている標準の .NET プロパティ パターンが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-149">The `Value` property in the example above wraps the dependency property, providing the standard .NET property pattern you're probably used to.</span></span>

<!--For more information, see [Dependency properties overview](../../../framework/wpf/advanced/dependency-properties-overview.md).-->

## <a name="events"></a><span data-ttu-id="7f539-150">イベント</span><span class="sxs-lookup"><span data-stu-id="7f539-150">Events</span></span>

<span data-ttu-id="7f539-151">WPF には、使い慣れている .NET 共通言語ランタイム (CLR) イベントの上に配置されたイベント処理システムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f539-151">WPF provides an eventing system that is layered on top of the .NET common language runtime (CLR) events you're familiar with.</span></span> <span data-ttu-id="7f539-152">これらの WPF イベントは、ルーティング イベントと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7f539-152">These WPF events are called routed events.</span></span>

<span data-ttu-id="7f539-153">ルーティング イベントは、`RoutedEvent` クラスのインスタンスによってバッキングされ、WPF イベント システムに登録される CLR イベントです。</span><span class="sxs-lookup"><span data-stu-id="7f539-153">A routed event is a CLR event that is backed by an instance of the `RoutedEvent` class and registered with the WPF event system.</span></span> <span data-ttu-id="7f539-154">イベント登録から取得された `RoutedEvent` インスタンスは、通常、ルーティング イベントを登録し、したがって "*所有*" しているクラスの `public static readonly` フィールド メンバーとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-154">The `RoutedEvent` instance obtained from event registration is typically retained as a `public static readonly` field member of the class that registers, and thus *owns* the routed event.</span></span> <span data-ttu-id="7f539-155">一意の名前を持つ CLR イベント ("*ラッパー*" イベントとも呼ばれます) への接続は、CLR イベントの `add` および `remove` 実装をオーバーライドすることにより得られます。</span><span class="sxs-lookup"><span data-stu-id="7f539-155">The connection to the identically named CLR event (which is sometimes termed the *wrapper* event) is accomplished by overriding the `add` and `remove` implementations for the CLR event.</span></span> <span data-ttu-id="7f539-156">ルーティング イベントのバッキングおよび接続メカニズムは、[依存関係プロパティ](#dependency-property)が、`DependencyProperty` クラスによってバッキングされ、WPF プロパティ システムに登録される CLR プロパティであるという概念に似ています。</span><span class="sxs-lookup"><span data-stu-id="7f539-156">The routed event backing and connection mechanism is conceptually similar to how a [dependency property](#dependency-property) is a CLR property that is backed by the `DependencyProperty` class and registered with the WPF property system.</span></span>

<span data-ttu-id="7f539-157">ルーティング イベントシステムの主な利点は、ハンドラーを探しているコントロール要素ツリーに対してイベントが *通知* されることです。</span><span class="sxs-lookup"><span data-stu-id="7f539-157">The main advantage of the routed event system is that events are *bubbled up* the control element tree looking for a handler.</span></span> <span data-ttu-id="7f539-158">たとえば、WPF には豊富なコンテンツ モデルがあるため、イメージ コントロールをボタン コントロールのコンテンツとして設定するとします。</span><span class="sxs-lookup"><span data-stu-id="7f539-158">For example, because WPF has a rich content model, you set an image control as the content of a button control.</span></span> <span data-ttu-id="7f539-159">イメージ コントロール上でマウスがクリックされると、マウス イベントが使用され、そのためにボタンが `Click` イベントを呼び出すきっかけとなるヒットテストが中断されることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-159">When the mouse is clicked on the image control, you would expect it to consume the mouse events, and thus break the hit-tests that cause a button to invoke the `Click` event.</span></span> <span data-ttu-id="7f539-160">従来の CLR イベント処理モデルでは、イメージとボタンの両方に同じハンドラーをアタッチすることで、この制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-160">In a traditional CLR eventing model, you would work around this limitation by attaching the same handler to both the image and the button.</span></span> <span data-ttu-id="7f539-161">しかしながらルーティング イベントシステムを使用すると、イメージ コントロール上で呼び出されたマウス イベント (選択など) は、親ボタン コントロールに通知されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-161">But with the routed event system, the mouse events invoked on the image control (such as selecting it) bubble up to the parent button control.</span></span>

<!--For more information, including other types of event models, see [Events overview](../../../framework/wpf/advanced/routed-events-overview.md).-->

## <a name="data-binding"></a><span data-ttu-id="7f539-162">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="7f539-162">Data binding</span></span>

<span data-ttu-id="7f539-163">WPF のデータ バインディングでは、アプリケーションでデータの表示や操作を行うための、シンプルかつ一貫した方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-163">WPF data binding provides a simple and consistent way for applications to present and interact with data.</span></span> <span data-ttu-id="7f539-164">要素は、共通言語ランタイム (CLR) オブジェクトおよび XML 形式のさまざまな種類のデータ ソースのデータにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="7f539-164">Elements can be bound to data from different types of data sources in the form of common language runtime (CLR) objects and XML.</span></span> <span data-ttu-id="7f539-165">WPF ではまた、ドラッグ アンド ドロップ操作によるデータ転送のメカニズムも提供されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-165">WPF also provides a mechanism for the transfer of data through drag-and-drop operations.</span></span>

<span data-ttu-id="7f539-166">データ バインディングとは、アプリケーションの UI とビジネス ロジックの間の接続を確立する処理です。</span><span class="sxs-lookup"><span data-stu-id="7f539-166">Data binding is the process that establishes a connection between the application UI and business logic.</span></span> <span data-ttu-id="7f539-167">バインドが適切に設定され、データから適切な通知が提供される場合、データの値が変更されると、そのデータにバインドされている要素に変更が自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-167">If the binding has the correct settings and the data provides the proper notifications, then, when the data changes its value, the elements that bound to the data reflect changes automatically.</span></span> <span data-ttu-id="7f539-168">データ バインディングには、要素内のデータの外部表現が変更された場合、基になるデータが自動的に更新されて変更が反映されるという意味もあります。</span><span class="sxs-lookup"><span data-stu-id="7f539-168">Data binding can also mean that if an outer representation of the data in an element changes, then the underlying data is automatically updated to reflect the change.</span></span> <span data-ttu-id="7f539-169">たとえば、ユーザーが TextBox 要素の値を編集すると、基になるデータ値がその変更を反映するように自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-169">For example, if the user edits the value in a TextBox element, the underlying data value is automatically updated to reflect that change.</span></span>

<span data-ttu-id="7f539-170">データ バインディングは、XAML で `{Binding}` マークアップ拡張を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-170">Data binding can be configured in XAML through the `{Binding}` markup extension.</span></span> <span data-ttu-id="7f539-171">次の例は、データ オブジェクトの `ButtonText` プロパティへのバインディングを示しています。</span><span class="sxs-lookup"><span data-stu-id="7f539-171">The following example demonstrates binding to a data object's `ButtonText` property.</span></span> <span data-ttu-id="7f539-172">そのバインディングが失敗した場合は、`Click Me!` の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f539-172">If that binding fails, the value of `Click Me!` is used.</span></span>

```xaml
<StackPanel>
    <Button Content="{Binding ButtonText, FallbackValue='Click Me!'}" />
</StackPanel>
```

<span data-ttu-id="7f539-173">詳しくは、「[データ バインディングの概要](../data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f539-173">For more information, see [Data binding overview](../data/data-binding-overview.md).</span></span>

## <a name="ui-components"></a><span data-ttu-id="7f539-174">UI コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7f539-174">UI components</span></span>

<span data-ttu-id="7f539-175">WPF には、`Button`、`Label`、`TextBox`、`Menu`、`ListBox` など、ほとんどの Windows アプリケーションで使用される共通の UI コンポーネントが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f539-175">WPF provides many of the common UI components that are used in almost every Windows application, such as `Button`, `Label`, `TextBox`, `Menu`, and `ListBox`.</span></span> <span data-ttu-id="7f539-176">これまで、これらのオブジェクトはコントロールと呼ばれてきました。</span><span class="sxs-lookup"><span data-stu-id="7f539-176">Historically, these objects have been referred to as controls.</span></span> <span data-ttu-id="7f539-177">WPF の SDK では、アプリケーションで表示可能なオブジェクトを表すクラスに、広義で「コントロール」という用語が使用され続けていますが、クラスは、表示可能な部分を持つために `Control` クラスを継承する必要がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f539-177">While the WPF SDK continues to use the term control to loosely mean any class that represents a visible object in an application, it's important to note that a class doesn't need to inherit from the `Control` class to have a visible presence.</span></span> <span data-ttu-id="7f539-178">`Control` クラスを継承するクラスには、`ControlTemplate` が含まれます。これを使用すると、コントロールのコンシューマーは、新しいサブクラスを作成しなくても、コントロールの外観を大幅に変更できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-178">Classes that inherit from the `Control` class contain a `ControlTemplate`, which allows the consumer of a control to radically change the control's appearance without having to create a new subclass.</span></span>

## <a name="styles-and-templates"></a><span data-ttu-id="7f539-179">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="7f539-179">Styles and templates</span></span>

<span data-ttu-id="7f539-180">WPF のスタイルとテンプレートは、アプリケーション、ドキュメント、または UI の設計者が視覚的に説得力のあるアプリケーションを作成し、製品に対して特定の外観を標準化できる、一連の機能 (スタイル、テンプレート、トリガー、およびストーリーボード) を表します。</span><span class="sxs-lookup"><span data-stu-id="7f539-180">WPF styling and templating refer to a suite of features (styles, templates, triggers, and storyboards) that allow an application, document, or UI designer to create visually compelling applications and to standardize on a particular look for their product.</span></span>

<span data-ttu-id="7f539-181">WPF のスタイルモデルのもう 1 つの機能は、表示とロジックの分離です。つまり、開発者が別の場所でプログラミング ロジックの作業をしているときに、設計者は XAML を使用してアプリケーションの外観について作業できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f539-181">Another feature of the WPF styling model is the separation of presentation and logic, which means designers can work on the appearance of an application with XAML while developers work on the programming logic elsewhere.</span></span>

<span data-ttu-id="7f539-182">また、スタイルとテンプレートの再利用を可能にするものである、リソースについて理解しておくことも重要です。</span><span class="sxs-lookup"><span data-stu-id="7f539-182">In addition, it's important to understand resources, which are what enable styles and templates to be reused.</span></span>

<span data-ttu-id="7f539-183">詳細については、[スタイルとテンプレート](../fundamentals/styles-templates-overview.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f539-183">For more information, see [Styles and templates](../fundamentals/styles-templates-overview.md).</span></span>

## <a name="resources"></a><span data-ttu-id="7f539-184">リソース</span><span class="sxs-lookup"><span data-stu-id="7f539-184">Resources</span></span>

<span data-ttu-id="7f539-185">WPF のリソースは、アプリケーションのさまざまな場所で再利用できるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7f539-185">WPF resources are objects that can be reused in different places in your application.</span></span> <span data-ttu-id="7f539-186">リソースの例としては、スタイル、テンプレート、色ブラシなどがあります。</span><span class="sxs-lookup"><span data-stu-id="7f539-186">Examples of resources include styles, templates, and color brushes.</span></span> <span data-ttu-id="7f539-187">リソースは、コードと XAML 形式の両方で定義および参照できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-187">Resources can be both defined and referenced in code and in XAML format.</span></span>

<span data-ttu-id="7f539-188">すべてのフレームワーク レベルの要素 (<xref:System.Windows.FrameworkElement> や <xref:System.Windows.FrameworkContentElement>) には、定義されたリソースを含む `Resources` プロパティ (<xref:System.Windows.ResourceDictionary> 型) があります。</span><span class="sxs-lookup"><span data-stu-id="7f539-188">Every framework-level element (<xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>) has a `Resources` property (which is a <xref:System.Windows.ResourceDictionary> type) that contains defined resources.</span></span> <span data-ttu-id="7f539-189">すべての要素はフレームワーク レベルの要素から継承されるため、すべての要素でリソースを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7f539-189">Since all elements inherit from a framework-level element, all elements can define resources.</span></span> <span data-ttu-id="7f539-190">ただし、XAML ドキュメントのルート要素にリソースを定義するのが最も一般的です。</span><span class="sxs-lookup"><span data-stu-id="7f539-190">It's most common, however, to define resources on a root element of a XAML document.</span></span>

<!--For more information, see [XAML Resources](../../../framework/wpf/advanced/xaml-resources.md).-->

## <a name="next-steps"></a><span data-ttu-id="7f539-191">次の手順</span><span class="sxs-lookup"><span data-stu-id="7f539-191">Next steps</span></span>

- [<span data-ttu-id="7f539-192">WPF アプリケーションを作成する。</span><span class="sxs-lookup"><span data-stu-id="7f539-192">Create a WPF application.</span></span>](/visualstudio/get-started/csharp/tutorial-wpf?bc=%252fdotnet%252fbreadcrumb%252ftoc.json&toc=%252fdotnet%252fdesktop-wpf%252ftoc.json)
- [<span data-ttu-id="7f539-193">.NET Framework との違いを調べる。</span><span class="sxs-lookup"><span data-stu-id="7f539-193">Explore the differences from .NET Framework.</span></span>](../migration/differences-from-net-framework.md)
- [<span data-ttu-id="7f539-194">XAML について学習する。</span><span class="sxs-lookup"><span data-stu-id="7f539-194">Learn about XAML.</span></span>](../fundamentals/xaml.md)
