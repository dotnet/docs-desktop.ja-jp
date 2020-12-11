---
title: x:Uid ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 7508d4917750d108b8843c6926938327b671ac06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985527"
---
# <a name="xuid-directive"></a>x:Uid ディレクティブ

マークアップ要素の一意の識別子を提供します。 多くのシナリオでは、この一意識別子は、XAML ローカリゼーションプロセスおよびツールによって使用されます。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`identifier`|コンシューマーによって解釈されるときに、ファイル内で一意である必要がある、手動で作成または自動生成された文字列 `x:Uid` 。|

## <a name="remarks"></a>注釈

[MS XAML] では、 `x:Uid` はディレクティブとして定義されます。 詳細については、「 [ \[ \] 5.3.6」セクション](/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。

`x:Uid` は、 `x:Name` XAML ローカライズのシナリオが原因で、ローカライズに使用される識別子がのプログラミングモデルへの影響に依存しないようにするため、両方とも不連続です `x:Name` 。 また、 `x:Name` は、xaml 名前スコープによって管理されます。ただし、は、 `x:Uid` xaml 言語で定義された一意性の強制の概念には適用されません。 XAML プロセッサは、広範な意味で (ローカライズプロセスに含まれていないプロセッサ)、値の一意性を強制することは想定されていません `x:Uid` 。 その責任は、値の発行元によって異なります。 `x:Uid`単一の XAML ソース内での値の一意性の予測は、専用のグローバリゼーションプロセスやツールなど、値のコンシューマーにとっては妥当です。 一般的な一意性モデルは、 `x:Uid` 値が XAML を表す XML エンコードファイル内で一意であることです。

特定の XAML スキーマについて十分な知識を持つツールは `x:Uid` 、マークアップでテキスト文字列値が検出されるすべてのケースではなく、真のローカライズ可能な文字列にのみ適用することができます。

フレームワークでは、 `x:Uid` 定義する型に属性を適用することによって、オブジェクトモデル内の特定のプロパティをの別名として指定でき <xref:System.Windows.Markup.UidPropertyAttribute> ます。 フレームワークで特定のプロパティが指定されている場合、 `x:Uid` 同じオブジェクトでとエイリアスを持つメンバーの両方を指定することは無効です。 とエイリアス化されたメンバーの両方が指定されている場合 `x:Uid` 、.NET XAML サービス API は通常、 <xref:System.Xaml.XamlDuplicateMemberException> この場合にをスローします。

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

`x:Uid`Wpf のローカリゼーションプロセスにおけるのロールと、XAML の BAML 形式の詳細については、「 [Wpf のグローバリゼーション](../framework/wpf/advanced/globalization-for-wpf.md)」または「」を参照してください。<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [WPF のグローバリゼーション](../framework/wpf/advanced/globalization-for-wpf.md)
