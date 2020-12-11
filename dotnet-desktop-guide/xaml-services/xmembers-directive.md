---
title: x:Members ディレクティブ
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980140"
---
# <a name="xmembers-directive"></a>x:Members ディレクティブ
マークアップで定義されているメンバーのセットを保持します。これは、親要素の x:Class に適用されます。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`className`|XAML 運用環境のバッキング クラスまたは部分クラスの名前。 「解説」を参照してください。|
|`oneOrMoreMembers`|メンバー定義を表す1つ以上のオブジェクト要素。 通常、これらは `x:Property` オブジェクト要素です。 「解説」を参照してください。|

## <a name="remarks"></a>注釈

.NET XAML サービスの実装では、のバッキングクラスまたは基になるメンバーの実装はありません `x:Members` 。 `x:Members` は、任意の型のメンバーとして存在できる特殊な XAML メンバーです。 XAML ノードストリームでは、 `x:Members` は、 `Members` xaml 言語の xaml 名前空間からという名前のメンバーとして表されます。 メンバーには、 `Members` オブジェクトの読み取り専用のジェネリックリストが含まれてい `Member` ます。 一般的なマークアップでは、個々のメンバーはプロパティ要素として指定され `x:Property` ます。 `x:Property` は、型のプロパティ専用のより正確な型であり、に割り当てることが `x:Member` できます。 詳細については、「 [X:Property ディレクティブ](xproperty-directive.md)」を参照してください。

マークアップでメンバーの定義を指定する手段として `x:Members` の実用的な使用法をサポートするため、メンバーを変更可能なクラスに関連付ける必要があります。 目的とするモデルは、`x:Members` が `x:Class` を指定する型のメンバーとして存在することです。 ただし、型とメンバーの関連付け、または動的メンバー定義の生成のためのメカニズムは、.NET XAML サービスレベルではサポートされていません。 これは、XAML のメンバーの定義をサポートするアプリケーション モデルがある個々のフレームワークに残されています。 一般に、XAML をマークアップ コンパイルするとともに、XAML と分離コードの統合または純粋な XAML からのアセンブリの生成を行う MSBUILD のビルド操作が、この機能をサポートするために必要です。

## <a name="xmembers-for-windows-workflow-foundation"></a>Windows Workflow Foundation 用の x:Members

Windows Workflow Foundation の場合 `x:Members` は、xaml で完全に構成されるカスタムアクティビティのメンバー、または分離コードを持つアクティビティデザイナーの xaml で定義された動的メンバーが含まれます。 `x:Class` は、XAML の運用環境のルート要素にも指定する必要があります。 これは、.NET XAML サービスレベルでは必須ではありませんが、カスタムアクティビティをサポートし、XAML を Windows Workflow Foundation XAML のビルドアクションによって XAML の実稼働が読み込まれる場合の要件になります。 `x:Members` は、を宣言するオブジェクト要素のマークアップ内の最初の子要素である必要があり `x:Class` ます。
