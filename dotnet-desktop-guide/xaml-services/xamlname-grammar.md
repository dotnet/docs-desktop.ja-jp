---
title: XamlName の文法
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 484406ff23c60389d71a638cd516c74d8d7edbe5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985419"
---
# <a name="xamlname-grammar"></a>XamlName の文法

XamlName 文法は、XAML 言語仕様 (MS XAML) で定義されている特定の文法です。これは便宜上、ここで再現します。

## <a name="from-the-xaml-specification"></a>XAML 仕様から

[XamlName 仕様は、型とプロパティに使用される一連の有効なシンボル識別子を識別する文法を定義します。

XamlName 型の文字列値は、次の文法に準拠している必要があります。

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Unicode 文字データベースで定義されている次の一般的なカテゴリ値を前提としています。

| Unicode カテゴリ   | 説明                   |
|--------------------|-------------------------------|
| ルー語                 | Letter, Uppercase (字、大文字)             |
| Ll                 | Letter, Lowercase (字、小文字)             |
| Lt                 | Letter, Titlecase (字、タイトル文字)             |
| Lm                 | Letter, Modifier (字、修飾)              |
| Lo                 | Letter, Other (字、その他)                 |
| Mn                 | マーク (スペースなし)             |
| Mc                 | Mark, Spacing Combining (結合文字、幅あり)       |
| Nd                 | Number、Decimal               |
| Nl                 | Number, Letter (数、字)                |

XAML は、プロパティおよびイベント修飾参照に使用される2番目の文法、DottedXamlName、およびアタッチされたメンバーに対しても定義します。 詳細については、「」 <xref:System.Windows.DependencyProperty> および「 [XAML の概要 (WPF)](../net/wpf/fundamentals/xaml.md)」を参照してください。

DottedXamlName 型の文字列値は、次の文法に準拠している必要があります。

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>注釈

完全な仕様については、「 [ \[ MS XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10))」を参照してください。
