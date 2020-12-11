---
title: XAML における xml:space の処理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: b05fb396850316c76721c72276ebb97f7e805ed3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980131"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="30c62-102">XAML における xml:space の処理</span><span class="sxs-lookup"><span data-stu-id="30c62-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="30c62-103">属性は、 `xml:space` オブジェクト要素内の有意な空白処理動作を宣言する XML 定義の属性です。</span><span class="sxs-lookup"><span data-stu-id="30c62-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="30c62-104">この動作は、が宣言されている要素内に含まれるすべてのコンテンツ (内部テキスト) に関連 `xml:space` し、子要素にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="30c62-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="30c62-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="30c62-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="30c62-106">\- または</span><span class="sxs-lookup"><span data-stu-id="30c62-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="30c62-107">注釈</span><span class="sxs-lookup"><span data-stu-id="30c62-107">Remarks</span></span>

<span data-ttu-id="30c62-108">XAML の属性の定義 `xml:space` (2 つの値を含む) は、 `xml:space` XML の W3C 仕様による "特別な属性" として定義されているから派生します。</span><span class="sxs-lookup"><span data-stu-id="30c62-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="30c62-109">属性の既定値 `xml:space` はリテラル値です `"default"` 。</span><span class="sxs-lookup"><span data-stu-id="30c62-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="30c62-110">値の `"default"` 場合、または `xml:space` がまったく指定されていない場合は、「 [XAML での空白の処理](white-space-processing.md)」で定義されているように、有意な空白の解析の動作が既定の処理になります。</span><span class="sxs-lookup"><span data-stu-id="30c62-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="30c62-111">オブジェクト要素のコンテンツ内の空白を保持するには、 `xml:space="preserve"` そのオブジェクト要素にを指定します。</span><span class="sxs-lookup"><span data-stu-id="30c62-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="30c62-112">ほとんどの解釈では、属性 `xml:space` の効果と属性の値が子要素にスコープ設定されます。</span><span class="sxs-lookup"><span data-stu-id="30c62-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="30c62-113">XAML での空白の処理の詳細については、「 [xaml での空白の処理](white-space-processing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c62-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="30c62-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="30c62-114">See also</span></span>

- [<span data-ttu-id="30c62-115">XAML での空白の処理</span><span class="sxs-lookup"><span data-stu-id="30c62-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="30c62-116">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="30c62-116">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
