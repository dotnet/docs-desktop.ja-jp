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
# <a name="-escape-sequence--markup-extension"></a>{} エスケープシーケンス/マークアップ拡張機能

属性値の XAML エスケープシーケンスを提供します。 エスケープシーケンスを使用すると、属性の後続の値をリテラルとして解釈できます。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>XAML プロパティ要素の使用

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|*literalValue*|エスケープシーケンスの後に続くリテラル文字列。 通常、この文字列には、左中かっこ ({または}) が含まれています。|

## <a name="remarks"></a>注釈

{}左中かっこ ({) を XAML のリテラル文字として使用できるように、エスケープシーケンス () が使用されます。

XAML リーダーは、通常、左中かっこ ({) を使用してマークアップ拡張機能のエントリポイントを表しますが、最初に次の文字をチェックして、右中かっこ (}) であるかどうかを確認します。 2つの中かっこ () が隣接している場合にのみ {} 、エスケープシーケンスと見なされます。

エスケープシーケンスが検出された場合、XAML リーダーは文字列の残りの部分を文字列として処理する必要があります。 ただし、エスケープシーケンスが型コンバーターを持つメンバーに適用されている場合、その文字列は XAML ライターによって解釈されるときに型変換が行われる可能性があります。

エスケープシーケンスはマークアップ拡張機能ではなく、クラスによってサポートされていません。 ただし、XAML リーダー (カスタム XAML リーダーを含む) は考慮する必要があります。

この方法では、引用符 (") をエスケープシーケンスとして使用することはできません。 コンテンツ以外のプロパティのプロパティ値として引用符を設定する必要がある場合は、プロパティ要素構文を使用し、プロパティ要素内に引用符を文字列として配置するか、XML 文字エンティティを使用します。 コンテンツプロパティの場合、引用符はコンテンツ全体にすることができます。

{}XAML マークアップ拡張機能が表示される場所に名前空間修飾子を含める必要がある XML 型を指定するときには、多くの場合、エスケープシーケンス () が必要です。 この場所には、XAML 属性値の開始と、等号 (=) の直後のマークアップ拡張機能が含まれます。 次の例は、XAML 属性値の開始時に表示される XML 名前空間のエスケープシーケンスを示しています。

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>関連項目

- [XAML の型コンバーターおよびマークアップ拡張機能](type-converters-and-markup-extensions.md)
- [XML 文字エンティティと XAML](xml-character-entities.md)
