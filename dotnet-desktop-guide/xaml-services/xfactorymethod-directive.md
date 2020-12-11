---
title: x:FactoryMethod ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980152"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod ディレクティブ
バッキング型を解決した後に、XAML プロセッサがオブジェクトを初期化するために使用する必要があるコンストラクター以外のメソッドを指定します。  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML 属性の使用、x:Arguments なし  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML 属性の使用法、x:Arguments as 要素  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 値  
  
|||  
|-|-|  
|`methodname`|として指定されたインスタンスを初期化するために XAML プロセッサが呼び出すメソッドの文字列メソッド名 `object` 。 「解説」を参照してください。|  
|`oneOrMoreObjectElements`|ファクトリメソッドのパラメーターを指定するオブジェクトの1つ以上のオブジェクト要素。 順序は重要です。これは、引数をファクトリメソッドに渡す順序を示します。|  
  
## <a name="remarks"></a>注釈  
 `methodname`がインスタンスメソッドの場合、修飾することはできません。  
  
 ファクトリメソッドとしての静的メソッドがサポートされています。 `methodname`が静的メソッドである場合、 `methodname` はの組み合わせとして提供されます。ここで、は、 `typeName.methodName` `typeName` 静的ファクトリメソッドを定義するクラスの名前を指定します。 `typeName` は、マップされた xmlns 内の型を参照する場合、プレフィックスで修飾できます。 `typeName` は、とは異なる型にすることができ `typeof(object)` ます。  
  
 ファクトリメソッドは、関連するオブジェクト要素をバッキングする型の宣言されたパブリックメソッドである必要があります。  
  
 ファクトリメソッドは、関連するオブジェクトに割り当て可能なインスタンスを返す必要があります。 ファクトリメソッドは null を返すことはできません。  
  
 `x:Arguments` ファクトリメソッドのシグネチャに最適な原則を使用して動作します。 照合では、最初にパラメーター数が評価されます。 パラメーターの数に一致する候補が複数ある場合は、パラメーターの型が評価され、最適な一致が決定されます。 この評価フェーズの後もあいまいさが残っている場合、XAML プロセッサの動作は未定義です。  
  
 `x:FactoryMethod`一般的な意味では、要素の使用法はプロパティ要素の使用ではありません。これは、ディレクティブマークアップが、包含するオブジェクト要素の型を参照しないためです。 要素の使用法が属性の使用法よりも低いことが想定されています。 `x:Arguments` (属性または要素の使用法) を要素の使用法と共に使用でき `x:FactoryMethod` ますが、これは使用方法のセクションでは特に示されていません。  
  
 `x:FactoryMethod` 要素は他のプロパティ要素の前に置く必要があるため、は要素として指定されたの前に記述する必要があり、 `x:Arguments` コンテンツ/内部テキスト/初期化テキストの前に記述する必要があります。  
  
## <a name="see-also"></a>関連項目

- [x:Arguments ディレクティブ](xarguments-directive.md)
