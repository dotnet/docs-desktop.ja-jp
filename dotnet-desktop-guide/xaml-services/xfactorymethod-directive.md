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
# <a name="xfactorymethod-directive"></a><span data-ttu-id="96cdb-102">x:FactoryMethod ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="96cdb-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="96cdb-103">バッキング型を解決した後に、XAML プロセッサがオブジェクトを初期化するために使用する必要があるコンストラクター以外のメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="96cdb-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="96cdb-104">XAML 属性の使用、x:Arguments なし</span><span class="sxs-lookup"><span data-stu-id="96cdb-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="96cdb-105">XAML 属性の使用法、x:Arguments as 要素</span><span class="sxs-lookup"><span data-stu-id="96cdb-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="96cdb-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="96cdb-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="96cdb-107">として指定されたインスタンスを初期化するために XAML プロセッサが呼び出すメソッドの文字列メソッド名 `object` 。</span><span class="sxs-lookup"><span data-stu-id="96cdb-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="96cdb-108">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96cdb-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="96cdb-109">ファクトリメソッドのパラメーターを指定するオブジェクトの1つ以上のオブジェクト要素。</span><span class="sxs-lookup"><span data-stu-id="96cdb-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="96cdb-110">順序は重要です。これは、引数をファクトリメソッドに渡す順序を示します。</span><span class="sxs-lookup"><span data-stu-id="96cdb-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96cdb-111">注釈</span><span class="sxs-lookup"><span data-stu-id="96cdb-111">Remarks</span></span>  
 <span data-ttu-id="96cdb-112">`methodname`がインスタンスメソッドの場合、修飾することはできません。</span><span class="sxs-lookup"><span data-stu-id="96cdb-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="96cdb-113">ファクトリメソッドとしての静的メソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="96cdb-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="96cdb-114">`methodname`が静的メソッドである場合、 `methodname` はの組み合わせとして提供されます。ここで、は、 `typeName.methodName` `typeName` 静的ファクトリメソッドを定義するクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="96cdb-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="96cdb-115">`typeName` は、マップされた xmlns 内の型を参照する場合、プレフィックスで修飾できます。</span><span class="sxs-lookup"><span data-stu-id="96cdb-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="96cdb-116">`typeName` は、とは異なる型にすることができ `typeof(object)` ます。</span><span class="sxs-lookup"><span data-stu-id="96cdb-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="96cdb-117">ファクトリメソッドは、関連するオブジェクト要素をバッキングする型の宣言されたパブリックメソッドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="96cdb-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="96cdb-118">ファクトリメソッドは、関連するオブジェクトに割り当て可能なインスタンスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="96cdb-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="96cdb-119">ファクトリメソッドは null を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="96cdb-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="96cdb-120">`x:Arguments` ファクトリメソッドのシグネチャに最適な原則を使用して動作します。</span><span class="sxs-lookup"><span data-stu-id="96cdb-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="96cdb-121">照合では、最初にパラメーター数が評価されます。</span><span class="sxs-lookup"><span data-stu-id="96cdb-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="96cdb-122">パラメーターの数に一致する候補が複数ある場合は、パラメーターの型が評価され、最適な一致が決定されます。</span><span class="sxs-lookup"><span data-stu-id="96cdb-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="96cdb-123">この評価フェーズの後もあいまいさが残っている場合、XAML プロセッサの動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="96cdb-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="96cdb-124">`x:FactoryMethod`一般的な意味では、要素の使用法はプロパティ要素の使用ではありません。これは、ディレクティブマークアップが、包含するオブジェクト要素の型を参照しないためです。</span><span class="sxs-lookup"><span data-stu-id="96cdb-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="96cdb-125">要素の使用法が属性の使用法よりも低いことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="96cdb-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="96cdb-126">`x:Arguments` (属性または要素の使用法) を要素の使用法と共に使用でき `x:FactoryMethod` ますが、これは使用方法のセクションでは特に示されていません。</span><span class="sxs-lookup"><span data-stu-id="96cdb-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="96cdb-127">`x:FactoryMethod` 要素は他のプロパティ要素の前に置く必要があるため、は要素として指定されたの前に記述する必要があり、 `x:Arguments` コンテンツ/内部テキスト/初期化テキストの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96cdb-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96cdb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="96cdb-128">See also</span></span>

- [<span data-ttu-id="96cdb-129">x:Arguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="96cdb-129">x:Arguments Directive</span></span>](xarguments-directive.md)
