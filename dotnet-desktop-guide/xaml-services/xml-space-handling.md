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
# <a name="xmlspace-handling-in-xaml"></a>XAML における xml:space の処理

属性は、 `xml:space` オブジェクト要素内の有意な空白処理動作を宣言する XML 定義の属性です。 この動作は、が宣言されている要素内に含まれるすべてのコンテンツ (内部テキスト) に関連 `xml:space` し、子要素にも適用されます。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object xml:space="preserve" />
```

 \- または

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>注釈

XAML の属性の定義 `xml:space` (2 つの値を含む) は、 `xml:space` XML の W3C 仕様による "特別な属性" として定義されているから派生します。

属性の既定値 `xml:space` はリテラル値です `"default"` 。 値の `"default"` 場合、または `xml:space` がまったく指定されていない場合は、「 [XAML での空白の処理](white-space-processing.md)」で定義されているように、有意な空白の解析の動作が既定の処理になります。

オブジェクト要素のコンテンツ内の空白を保持するには、 `xml:space="preserve"` そのオブジェクト要素にを指定します。

ほとんどの解釈では、属性 `xml:space` の効果と属性の値が子要素にスコープ設定されます。

XAML での空白の処理の詳細については、「 [xaml での空白の処理](white-space-processing.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [XAML での空白の処理](white-space-processing.md)
- [XAML の概要 (WPF)](../net/wpf/fundamentals/xaml.md)
