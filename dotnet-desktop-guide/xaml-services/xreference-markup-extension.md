---
title: x:Reference のマークアップ拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980095"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="bf706-102">x:Reference のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="bf706-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="bf706-103">XAML マークアップの他の場所で宣言されているインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="bf706-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="bf706-104">参照が要素のを参照して `x:Name` います。</span><span class="sxs-lookup"><span data-stu-id="bf706-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="bf706-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="bf706-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="bf706-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="bf706-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="bf706-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="bf706-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="bf706-108">参照された `x:Name` インスタンスの値 (または、指定されたプロパティの値 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> )。</span><span class="sxs-lookup"><span data-stu-id="bf706-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bf706-109">注釈</span><span class="sxs-lookup"><span data-stu-id="bf706-109">Remarks</span></span>

<span data-ttu-id="bf706-110">`x:Reference` WPF などの特定のフレームワークで実装されていた要素参照の概念に対する XAML 言語レベルのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf706-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="bf706-111">x:Reference と WPF</span><span class="sxs-lookup"><span data-stu-id="bf706-111">x:Reference and WPF</span></span>

<span data-ttu-id="bf706-112">WPF および XAML 2006 では、要素参照は、バインディングのフレームワークレベルの機能によってアドレス指定され <xref:System.Windows.Data.Binding.ElementName%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="bf706-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="bf706-113">ほとんどの WPF アプリケーションとシナリオでは、 <xref:System.Windows.Data.Binding.ElementName%2A> バインドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf706-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="bf706-114">この一般的なガイダンスの例外として、データコンテキストがある場合や、データバインディングが実用的ではなく、マークアップコンパイルが関係しない場合などがあります。</span><span class="sxs-lookup"><span data-stu-id="bf706-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="bf706-115">`x:Reference` は、XAML 2009 で定義されている構造体です。</span><span class="sxs-lookup"><span data-stu-id="bf706-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="bf706-116">WPF では XAML 2009 の機能を使用できますが、WPF マークアップ コンパイルされていない XAML に限定されます。</span><span class="sxs-lookup"><span data-stu-id="bf706-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="bf706-117">マークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 言語のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bf706-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
