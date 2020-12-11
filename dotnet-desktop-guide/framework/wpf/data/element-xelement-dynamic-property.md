---
title: Element (XElement 動的プロパティ)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974641"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="4d831-102">Element (XElement 動的プロパティ)</span><span class="sxs-lookup"><span data-stu-id="4d831-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="4d831-103">指定された展開名に対応する子要素のインスタンスを取得するためのインデクサーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d831-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d831-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d831-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="4d831-105">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="4d831-105">Property value/return value</span></span>

<span data-ttu-id="4d831-106">`XElement Item(String expandedName)` 型のインデクサー。</span><span class="sxs-lookup"><span data-stu-id="4d831-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="4d831-107">このインデクサーは、展開名のパラメーターを取得し、対応する <xref:System.Xml.Linq.XElement> を返します。指定された名前を持つ要素がない場合は、`null` を返します。</span><span class="sxs-lookup"><span data-stu-id="4d831-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d831-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d831-108">Remarks</span></span>

<span data-ttu-id="4d831-109">このプロパティは、<xref:System.Xml.Linq.XContainer.Element%2A> クラスの <xref:System.Xml.Linq.XContainer?displayProperty=fullName> メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="4d831-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d831-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d831-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="4d831-111">XElement クラスの動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="4d831-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="4d831-112">要素</span><span class="sxs-lookup"><span data-stu-id="4d831-112">Elements</span></span>](elements-xelement-dynamic-property.md)
