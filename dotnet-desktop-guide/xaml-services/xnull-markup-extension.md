---
title: x:Null のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7f7c4cd44448b6e4e8b8934a63b56b910ce0428a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980101"
---
# <a name="xnull-markup-extension"></a>x:Null のマークアップ拡張機能

`null`XAML メンバーの値としてを指定します。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>注釈

C# および C++ での null 参照のキーワードが null です。 Null 参照の Microsoft Visual Basic キーワードはです `Nothing` が、 `{x:Null}` xaml に関連付けた分離コード言語に関係なく、常に xaml の使用法としてを使用します。

`x:Null`マークアップ拡張機能には、設定可能なプロパティはありません。

Null 使用は、多くの場合、CLR 値の XAML メンバー公開に関連付けられてい <xref:System.Nullable%601> ます。

`x:Null`マークアップ拡張機能は、すべての XAML マークアップ拡張機能と同様に、中かっこ () を使用して、 `{,}` リテラルまたはイベントハンドラー参照以外の属性値の処理をエスケープします。 属性構文は、このマークアップ拡張機能で最も頻繁に使用される構文です。 オブジェクト要素の構文は `<x:Null />` 技術的には可能ですが、 `x:Null` マークアップ拡張機能に位置指定パラメーターも構築引数もないため、ほとんど使用されません。

マークアップ拡張機能の詳細については、「 [マークアップ拡張機能と WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)」を参照してください。

.NET XAML サービスでは、このマークアップ拡張機能の処理はクラスによって定義され <xref:System.Windows.Markup.NullExtension> ます。

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

`null`は必ずしも参照型の依存関係プロパティの最初の未設定値ではないことに注意してください。 初期の既定値は、依存関係プロパティごとに異なる場合があり、プロパティ固有のメタデータに基づいている場合もあります。 多くの依存関係プロパティは、 `null` 検証コールバックの実装により、マークアップまたはコードによって値として受け入れられません。 依存関係プロパティの詳細については、「[依存関係プロパティの概要](../framework/wpf/advanced/dependency-properties-overview.md)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [XAML の概要 (WPF)](../net/wpf/fundamentals/xaml.md)
- [マークアップ拡張機能と WPF XAML](../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
