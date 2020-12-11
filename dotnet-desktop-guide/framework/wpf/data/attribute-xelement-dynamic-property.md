---
title: Attribute (XElement 動的プロパティ)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985116"
---
# <a name="attribute-xelement-dynamic-property"></a>Attribute (XElement 動的プロパティ)

指定された展開名に対応する属性のインスタンスの取得に使用するインデクサーを取得します。

## <a name="syntax"></a>構文

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

`XAttribute Item(String expandedName)` 型のインデクサー。 このインデクサーは、指定された属性の展開名を受け取り、対応する <xref:System.Xml.Linq.XAttribute> を返します。指定された名前を持つ属性がない場合は、`null` を返します。

## <a name="remarks"></a>Remarks

このプロパティは、<xref:System.Xml.Linq.XElement.Attribute%2A> クラスの <xref:System.Xml.Linq.XElement?displayProperty=fullName> メソッドに相当します。

## <a name="see-also"></a>関連項目

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [XElement クラスの動的プロパティ](attribute-xelement-dynamic-property.md)
- [[値]](value-xattribute-dynamic-property.md)
