---
title: XAML のコレクションおよびコレクション型
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985759"
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML のコレクションとコレクション型

この記事では、コレクションをサポートするための型のプロパティを定義する方法と、親オブジェクトの要素またはプロパティ要素の子要素としてコレクション項目をインスタンス化するための XAML 構文をサポートする方法について説明します。

## <a name="xaml-collection-concepts"></a>XAML コレクションの概念

概念的には、xaml オブジェクト要素または XAML プロパティ要素のスコープ内に複数の子項目がある XAML 内のリレーションシップは、コレクションとして実装する必要があります。 そのコレクションは、そのリレーションシップの親である XAML 型の特定の XAML プロパティに関連付けられている必要があります。 XAML プロセッサは、マークアップ内の各項目をバッキングコレクションプロパティの新しく追加された項目として割り当てることを想定しているため、プロパティはコレクションである必要があります。

XAML 言語レベルでは、コレクションサポートの正確な要件は完全には定義されていません。 コレクションがリストまたはディクショナリ (両方ではない) のいずれかであるという概念は、XAML 言語レベルで定義されていますが、どちらのバッキング型でも、リストまたはディクショナリは、XAML 言語で定義されていません。

.NET XAML サービスでは、XAML コレクションのサポートの概念が、.NET バッキング型の観点からより明確に定義されています。 具体的には、コレクションの XAML サポートは、.net の一般的なプログラミングでリストおよびディクショナリに使用されるいくつかの .NET の概念と Api に基づいています。

1. <xref:System.Collections.IList>インターフェイスはリストコレクションを示します。

2. インターフェイスは、 <xref:System.Collections.IDictionary> ディクショナリコレクションを示します。

3. <xref:System.Array> は配列を表し、配列はメソッドをサポートし <xref:System.Collections.IList> ます。

これらの各コレクションの概念では、.NET XAML サービスの XAML プロセッサは、 `Add` コレクションプロパティの型の特定のインスタンスに対してメソッドを呼び出すことを想定しています。 また、シリアル化のシナリオでは、XAML プロセッサによって、リスト、ディクショナリ、または配列内の各項目について、各コレクションに固有の "項目" の概念に基づいて、個別の XAML 型のインスタンスが生成されます。 これらの項目は次のとおりです。 <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType> ; <xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType> 、の明示的な <xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType> <xref:System.Array> 。

## <a name="generic-collections"></a>ジェネリックコレクション

ジェネリックコレクションは、一般的な .NET プログラミングに役立ち、XAML コレクションプロパティにも使用できます。 ただし、ジェネリックインターフェイス <xref:System.Collections.Generic.IList%601> と <xref:System.Collections.Generic.IDictionary%602> は、.Net xaml サービスの xaml プロセッサによって、非ジェネリックまたはと同等のものとして識別されません <xref:System.Collections.IList> <xref:System.Collections.IDictionary> 。 ジェネリックコレクションプロパティの型の推奨される方法は、インターフェイスを実装するのではなく、クラスまたはから派生することです <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.Dictionary%602> 。 これらのクラスは、非ジェネリックインターフェイスを実装します。したがって、基本実装で XAML コレクションの予想されるサポートが含まれます。

## <a name="read-only-collections-and-initialization-logic"></a>Read-Only コレクションと初期化ロジック

.NET プログラミングでは、コレクションの値を保持する任意のプロパティを読み取り専用コレクションとして作成するための一般的なデザインパターンです。 このパターンでは、コレクションプロパティを所有するインスタンスが、コレクションに対して実行される処理をより適切に制御できるようにします。 具体的には、プロパティを設定することによって、既存のコレクション全体が誤って置換されるのを防ぐことができます。 このパターンでは、呼び出し元によるコレクションへのアクセスは、コレクション型やなどの関連するコレクションインターフェイスでサポートされているメソッドまたはプロパティを呼び出すことによって行う必要があり <xref:System.Collections.IList> ます。

このパターンを使用すると、読み取り専用のコレクションプロパティを公開するすべてのクラスは、最初に空のコレクションを保持するためにそのプロパティを初期化する必要があります。 通常、初期化は、クラスの構築動作の一部として実行されます。 Xaml では、通常、このようなロジックがパラメーターなしのコンストラクターによって参照されることが重要です。 XAML では、プロパティを処理する前にパラメーターなしのコンストラクターが一般に呼び出されるためです (コレクションプロパティなど)。

## <a name="xaml-type-system-support-and-collections"></a>XAML 型システムのサポートとコレクション

Xaml の解析とコレクションプロパティの設定またはシリアル化の基本的なメカニズムに加えて、.NET XAML サービスに実装されている XAML 型システムには、XAML のコレクションに関連するいくつかのデザイン機能が含まれています。

1. <xref:System.Xaml.XamlType.IsCollection%2A> xaml 型が XAML コレクションサポートを提供する型によってサポートされている場合に true を返します。

2. <xref:System.Xaml.XamlType.IsDictionary%2A> とは、 <xref:System.Xaml.XamlType.IsArray%2A> XAML 型でサポートされているコレクションモードをさらに識別できます。 .NET XAML サービスと XAML 型システムに基づくカスタム XAML プロセッサで、既存の実装に基づいていない場合は、どのコレクションモードが使用されているかを把握して <xref:System.Xaml.XamlWriter> おく必要があります。これは、どのメソッドを使用してコレクション処理を呼び出すかを知るためです。

3. 前の各プロパティ値は、XAML 型ののオーバーライドによって影響を受ける可能性があり <xref:System.Xaml.XamlType.LookupCollectionKind%2A> ます。
