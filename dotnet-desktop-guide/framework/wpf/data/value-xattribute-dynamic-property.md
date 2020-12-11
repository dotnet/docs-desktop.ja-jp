---
title: Value (XAttribute 動的プロパティ)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.openlocfilehash: 32c15a89a976b5f9af12f040c43e724a25357ead
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985787"
---
# <a name="value-xattribute-dynamic-property"></a><span data-ttu-id="50c71-102">Value (XAttribute 動的プロパティ)</span><span class="sxs-lookup"><span data-stu-id="50c71-102">Value (XAttribute dynamic property)</span></span>

<span data-ttu-id="50c71-103">XML 属性の値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="50c71-103">Gets or sets the value of the XML attribute.</span></span>

## <a name="syntax"></a><span data-ttu-id="50c71-104">構文</span><span class="sxs-lookup"><span data-stu-id="50c71-104">Syntax</span></span>

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="50c71-105">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="50c71-105">Property value/return value</span></span>

<span data-ttu-id="50c71-106">この属性の値を表す <xref:System.String> です。</span><span class="sxs-lookup"><span data-stu-id="50c71-106">A <xref:System.String> containing the value of this attribute.</span></span>

## <a name="exceptions"></a><span data-ttu-id="50c71-107">例外</span><span class="sxs-lookup"><span data-stu-id="50c71-107">Exceptions</span></span>

|<span data-ttu-id="50c71-108">例外の種類</span><span class="sxs-lookup"><span data-stu-id="50c71-108">Exception type</span></span>|<span data-ttu-id="50c71-109">条件</span><span class="sxs-lookup"><span data-stu-id="50c71-109">Condition</span></span>|
| - |---------------|
|<xref:System.ArgumentNullException>|<span data-ttu-id="50c71-110">設定時に `value` が `null` である場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="50c71-110">When setting, the `value` is `null`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="50c71-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="50c71-111">Remarks</span></span>

<span data-ttu-id="50c71-112">このプロパティは、<xref:System.Xml.Linq.XAttribute.Value%2A> クラスの <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> プロパティに相当します。ただし、この動的プロパティは変更通知もサポートします。</span><span class="sxs-lookup"><span data-stu-id="50c71-112">This property is equivalent to the <xref:System.Xml.Linq.XAttribute.Value%2A> property of the <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> class, but this dynamic property also supports change notifications.</span></span>

## <a name="see-also"></a><span data-ttu-id="50c71-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="50c71-113">See also</span></span>

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [<span data-ttu-id="50c71-114">XAttribute クラスの動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="50c71-114">XAttribute class dynamic properties</span></span>](value-xattribute-dynamic-property.md)
- [<span data-ttu-id="50c71-115">属性</span><span class="sxs-lookup"><span data-stu-id="50c71-115">Attribute</span></span>](attribute-xelement-dynamic-property.md)
