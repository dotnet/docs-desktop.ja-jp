---
title: '{} エスケープシーケンスマークアップ拡張機能'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985752"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="f69c5-102">{} エスケープシーケンス/マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="f69c5-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="f69c5-103">属性値の XAML エスケープシーケンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f69c5-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="f69c5-104">エスケープシーケンスを使用すると、属性の後続の値をリテラルとして解釈できます。</span><span class="sxs-lookup"><span data-stu-id="f69c5-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="f69c5-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="f69c5-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="f69c5-106">XAML プロパティ要素の使用</span><span class="sxs-lookup"><span data-stu-id="f69c5-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="f69c5-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="f69c5-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="f69c5-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="f69c5-108">*literalValue*</span></span>|<span data-ttu-id="f69c5-109">エスケープシーケンスの後に続くリテラル文字列。</span><span class="sxs-lookup"><span data-stu-id="f69c5-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="f69c5-110">通常、この文字列には、左中かっこ ({または}) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f69c5-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="f69c5-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f69c5-111">Remarks</span></span>

<span data-ttu-id="f69c5-112">{}左中かっこ ({) を XAML のリテラル文字として使用できるように、エスケープシーケンス () が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f69c5-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="f69c5-113">XAML リーダーは、通常、左中かっこ ({) を使用してマークアップ拡張機能のエントリポイントを表しますが、最初に次の文字をチェックして、右中かっこ (}) であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f69c5-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="f69c5-114">2つの中かっこ () が隣接している場合にのみ {} 、エスケープシーケンスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="f69c5-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="f69c5-115">エスケープシーケンスが検出された場合、XAML リーダーは文字列の残りの部分を文字列として処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f69c5-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="f69c5-116">ただし、エスケープシーケンスが型コンバーターを持つメンバーに適用されている場合、その文字列は XAML ライターによって解釈されるときに型変換が行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f69c5-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="f69c5-117">エスケープシーケンスはマークアップ拡張機能ではなく、クラスによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f69c5-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="f69c5-118">ただし、XAML リーダー (カスタム XAML リーダーを含む) は考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f69c5-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="f69c5-119">この方法では、引用符 (") をエスケープシーケンスとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f69c5-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="f69c5-120">コンテンツ以外のプロパティのプロパティ値として引用符を設定する必要がある場合は、プロパティ要素構文を使用し、プロパティ要素内に引用符を文字列として配置するか、XML 文字エンティティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f69c5-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="f69c5-121">コンテンツプロパティの場合、引用符はコンテンツ全体にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f69c5-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="f69c5-122">{}XAML マークアップ拡張機能が表示される場所に名前空間修飾子を含める必要がある XML 型を指定するときには、多くの場合、エスケープシーケンス () が必要です。</span><span class="sxs-lookup"><span data-stu-id="f69c5-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="f69c5-123">この場所には、XAML 属性値の開始と、等号 (=) の直後のマークアップ拡張機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f69c5-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="f69c5-124">次の例は、XAML 属性値の開始時に表示される XML 名前空間のエスケープシーケンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f69c5-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="f69c5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f69c5-125">See also</span></span>

- [<span data-ttu-id="f69c5-126">XAML の型コンバーターおよびマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="f69c5-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="f69c5-127">XML 文字エンティティと XAML</span><span class="sxs-lookup"><span data-stu-id="f69c5-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
